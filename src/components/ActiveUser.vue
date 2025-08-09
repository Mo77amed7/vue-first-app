<template>
  <section>
    <ul>
      <li>
        <h2>{{ name }}</h2>
        <h3>{{ age }}</h3>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: true,
    },
    age: {
      type: String,
      required: true,
    },
  },
  data() {
    return {};
  },
  methods: {},
};
</script>
