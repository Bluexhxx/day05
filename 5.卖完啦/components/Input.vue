<template>
  <p>
    <input v-model.number="obj.count" type="number" min="0" />
    <span>{{ obj.goodsName }}</span>
    <span v-show="obj.count == 0">卖光啦！！</span>
  </p>
</template>

<script>
export default {
  props: ["obj"],
};
</script>

<style></style>
