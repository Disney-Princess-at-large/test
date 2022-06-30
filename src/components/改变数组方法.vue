<template>
    <div>
        <div>
            <!-- 观察数组的哪些方法 可以导致vue的视图发生更新 -->
            <ul>
            <li v-for="item in arr" :key="item">{{ item }}</li>
            </ul>
            <button @click="reverse">数组翻转</button>
            <button @click="slice">截取前3个</button>
            <button @click="change2">更新第一个元素值</button>
        </div>
        <div>
            <h1>{{ obj.a }}</h1>
            <button @click="change">改变</button>
            <h1>{{ obj1 && obj1.a }}</h1>
            <button @click="change1">改变</button>
        </div>
    </div>
  
</template>

<script>
export default {
  name: "VArr",

  data() {
    return {
      arr: [1, 2, 3, 4, 5],
      obj: {
        b: 10,
        c: 12,
      },
      obj1: {},
    };
  },
  mounted() {},
  methods: {
    reverse() {
      this.arr.reverse();
    },
    slice() {
      // this.arr.slice(索引号, 截取的长度);
      this.arr.slice(0, 3);
      console.log(this.arr.slice(0, 3));
      console.log(this.arr);
      // 只要让原数组 发生改变 页面的数据就会改变

      // 解决方案
      this.arr = this.arr.slice(0, 3);
    },
    change2() {
      // this.arr[0] = 1000;
      // console.log(this.arr);
      
      // 解决方案
      // $set(需要添加属性的目标的对象， 属性， 属性对应具体的值)
      this.$set(this.arr, 0, 1000);
    },
    change() {
      // this.obj.a = 10;
      // console.log(this.obj);
      // 解决方法
      // this.obj = {
      //   b: 10,
      //   c: 12,
      //   a: 10,
      // };
      // console.log(this.obj);
      // 只要是在这个点击之后 再去修改a的值，可以去发视图的更新
      this.$set(this.obj, "a", 10);
      console.log("===", this.obj);
    },
    change1() {
      this.obj1 = {
        a: 10,
      };
    },
    }
};
</script>

<style scoped>
</style>