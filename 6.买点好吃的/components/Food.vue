<template></template>

<template>
  <div>
    <span>{{ shopName }}</span>
    <button @click="addCount(i)">+</button>
    <span> {{ count }} </span>
    <button @click="subCount(i)">-</button>
  </div>
</template>

<script>
export default {
  props: ["shopName", "count", "i"],
  methods: {
    addCount(index) {
      this.$emit("EaddFn", index); // s->f
    },
    subCount(index) {
      this.$emit("EsubFn", index);
    },
  },
};
</script>

<style></style>
