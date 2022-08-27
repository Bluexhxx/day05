<template>
  <div>
    <dog></dog>
    <dog></dog>
    <dog></dog>
    <dog></dog>
    <dog></dog>
    <dog></dog>
  </div>
</template>

<script>
import dog from '@/components/dog1.vue'
export default {
  components:{
    dog,
  }
}
</script>

<style>
div{
  width: 60%;
}
</style>