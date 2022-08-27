<template>
  <div class="box">
    <img :src=imgUrl />
    <span>{{ dogName }}</span>
  </div>
</template>

<script>
export default {
  props: ["imgUrl", "dogName"],
  data() {
    return {
      colorStr: ["red", "blue", "pink", "skyblue", "green"],
    };
  },
  methods: {
    ll() {
      console.log(this.obj);
    },
  },
};
</script>

<style scoped>
div.box {
  float: left;
  width: 200px;
  height: 230px;
  border: solid 1px black;
  text-align: center;
}
div > img {
  width: 100%;
  height: 200px;
}
.scolor {
  background-color: aquamarine;
}
</style>
