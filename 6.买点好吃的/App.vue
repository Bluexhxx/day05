<template>
  <div>
    <p>商品清单如下：</p>
    <p v-for="(item, index) in shopArr" :key="'B' + index">
      {{ item.shopName }}{{ item.price }}元/份
    </p>
    <hr />
    <Food
      v-for="(item, index) in shopArr"
      :key="'A' + index"
      :i="index"
      :shopName="item.shopName"
      :count="item.count"
      @EaddFn="addFn"
      @EsubFn="subFn"
    ></Food>
    <p>总价为：{{ allPrice }}</p>
  </div>
</template>

<script>
import Food from "@/components/Food";
export default {
  components: {
    Food,
  },
  methods: {
    addFn(index) {
      this.shopArr[index].count++;
    },
    subFn(index) {
      this.shopArr[index].count > 0 && this.shopArr[index].count--;
    },
  },
  computed: {
    allPrice() {
      return this.shopArr.reduce(
        (pre, curr) => (pre += curr.count * curr.price),
        0
      );
    },
  },
  data() {
    return {
      shopArr: [
        {
          shopName: "可比克薯片",
          price: 5.5,
          count: 0,
        },
        {
          shopName: "草莓酱",
          price: 3.5,
          count: 0,
        },
        {
          shopName: "红烧肉",
          price: 55,
          count: 0,
        },
        {
          shopName: "方便面",
          price: 12,
          count: 0,
        },
      ],
    };
  },
};
</script>

<style></style>
