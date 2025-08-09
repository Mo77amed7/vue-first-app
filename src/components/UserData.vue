<template>
  <section>
    <h2>User Data</h2>
    <form @submit.prevent="addUser">
      <div>
        <label for="name">Name</label>
        <input type="text" v-model="userName" />
      </div>
      <div>
        <label for="age">Age</label>
        <input type="number" v-model="userAge" min="1"/>
      </div>
      <div>
        <button>Set User Data</button>
      </div>
    </form>
  </section>
</template>
<script>
export default {
  emits: ["add-user"],
  data() {
    return {
      userName: "",
      userAge: "",
    };
  },
  methods: {
    addUser() {
      this.$emit("add-user", this.userName, this.userAge);
    },
  },
};
</script>
<style scoped>
form {
  width: 100%;
  background-color: rgb(192, 216, 231);
  padding: 20px;
  text-align: center;
}
form div {
  margin: 5px auto;
  width: 45%;
  display: flex;
  justify-content: space-between;
}

input {
  padding: 5px;
  border: none;
  outline: none;
}
label {
  font-weight: bold;
  color: #58004d;
}
button {
  width: 100%;
  margin: 5px auto;
}
</style>
