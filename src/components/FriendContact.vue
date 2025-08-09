<template>
  <header><h1>Friends</h1></header>
  <section style="text-align: center; width: 90%; margin: auto">
    <h2>{{ name }} {{ isFavorable ? "(Favorable)" : "" }}</h2>
    <button @click="toggleBtn">
      {{ visibleContact ? "Hide" : "View" }} Contact
    </button>
    <button @click="toggleFavorable">
      {{ isFavorable ? "Hide" : "View" }}
    </button>
    <ul v-if="visibleContact">
      <li><strong>Age:</strong> {{ age }}</li>
      <li><strong>Email:</strong> {{ mail }}</li>
    </ul>
  </section>
</template>

<script>
export default {
  emits: ["toggle-favorite"],
  props: {
    id: {
      type: Number,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    age: {
      type: Number,
      required: true,
    },
    mail: {
      type: String,
      required: true,
    },
    isFavorable: {
      type: Boolean,
      required: false,
      default: false,
    },
  },
  data() {
    return {
      visibleContact: false,
    };
  },
  methods: {
    toggleBtn() {
      this.visibleContact = !this.visibleContact;
    },
    toggleFavorable() {
      this.$emit("toggle-favorite", this.id);
    },
  },
};
</script>
