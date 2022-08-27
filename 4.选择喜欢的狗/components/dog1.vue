<template>
  <div class="box">
    <img :src="imgUrl" />
    <span :style="{ backgroundColor: colorStr }" @click="btn">{{
      dogName
    }}</span>
  </div>
</template>

<script>
export default {
  props: ["imgUrl", "dogName"],
  data() {
    return {
      colorStr: '',
    };
  },
  methods: {
    btn() {
      this.$emit("liShow",this.dogName)
      this.colorStr = `rgb(${Math.floor(Math.random() * 256)}, ${Math.floor(
        Math.random() * 256
      )}, ${Math.floor(Math.random() * 256)})`;
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
