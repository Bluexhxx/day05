<template>
  <div>
    <table>
      <my-input
        is="MyInput"
        v-for="(item, index) in goodsArr"
        :key="index"
        :obj="item"
      ></my-input>
    </table>
    <p>All Number:{{ sumNumber }}</p>
  </div>
</template>

<script>
import MyInput from "@/components/Input";
export default {
  components: {
    MyInput,
  },
  methods: {
    getNum() {},
  },
  computed: {
    sumNumber: {
      get() {
        return this.goodsArr.reduce((pre, curr) => (pre += curr.count),0);
      },
      // set(val) {},
    },
  },
  data() {
    return {
      goodsArr: [
        {
          count: 0,
          goodsName: "Watermelon",
        },
        {
          count: 0,
          goodsName: "Banana",
        },
        {
          count: 0,
          goodsName: "Orange",
        },
        {
          count: 0,
          goodsName: "Pineapple",
        },
        {
          count: 0,
          goodsName: "Strawberry",
        },
      ],
    };
  },
};
</script>

<style></style>
