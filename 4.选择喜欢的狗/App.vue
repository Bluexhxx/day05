<template>
  <div>
    <dog
      v-for="(item, index) in arr"
      :key="index"
      :imgUrl="item.dogImgUrl"
      :dogName="item.dogName"
      @liShow="selDog"
    ></dog>
    <ul>
      <li v-for="(item, index) in loveArr" :key="index">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
import dog from "@/components/dog1.vue";
export default {
  components: {
    dog,
  },
  methods: {
    selDog(dogName) {
      console.log(dogName);
      this.loveArr.push(dogName);
    },
  },
  data() {
    return {
      loveArr: [],
      arr: [
        {
          dogImgUrl:
            "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fn.sinaimg.cn%2Fsinakd20111%2F96%2Fw2048h2048%2F20211126%2F3616-a88be01fc72e6eab133638676bf3188b.jpg&refer=http%3A%2F%2Fn.sinaimg.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1664103803&t=766bbfe2e72dec50e4f3ebb07cc4d796",
          dogName: "博美",
        },
        {
          dogImgUrl:
            "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fn.sinaimg.cn%2Fsinakd20111%2F96%2Fw2048h2048%2F20211126%2F3616-a88be01fc72e6eab133638676bf3188b.jpg&refer=http%3A%2F%2Fn.sinaimg.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1664103803&t=766bbfe2e72dec50e4f3ebb07cc4d796",
          dogName: "泰迪",
        },
        {
          dogImgUrl:
            "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fn.sinaimg.cn%2Fsinakd20111%2F96%2Fw2048h2048%2F20211126%2F3616-a88be01fc72e6eab133638676bf3188b.jpg&refer=http%3A%2F%2Fn.sinaimg.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1664103803&t=766bbfe2e72dec50e4f3ebb07cc4d796",
          dogName: "金毛",
        },
        {
          dogImgUrl:
            "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fn.sinaimg.cn%2Fsinakd20111%2F96%2Fw2048h2048%2F20211126%2F3616-a88be01fc72e6eab133638676bf3188b.jpg&refer=http%3A%2F%2Fn.sinaimg.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1664103803&t=766bbfe2e72dec50e4f3ebb07cc4d796",
          dogName: "哈士奇",
        },
        {
          dogImgUrl:
            "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fn.sinaimg.cn%2Fsinakd20111%2F96%2Fw2048h2048%2F20211126%2F3616-a88be01fc72e6eab133638676bf3188b.jpg&refer=http%3A%2F%2Fn.sinaimg.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1664103803&t=766bbfe2e72dec50e4f3ebb07cc4d796",
          dogName: "阿拉斯加",
        },
        {
          dogImgUrl:
            "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fn.sinaimg.cn%2Fsinakd20111%2F96%2Fw2048h2048%2F20211126%2F3616-a88be01fc72e6eab133638676bf3188b.jpg&refer=http%3A%2F%2Fn.sinaimg.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1664103803&t=766bbfe2e72dec50e4f3ebb07cc4d796",
          dogName: "萨摩耶",
        },
      ],
    };
  },
};
</script>

<style>
div {
  width: 60%;
}
</style>
