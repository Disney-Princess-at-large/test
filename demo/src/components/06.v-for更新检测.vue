<template>
  <div>
    <ul>
      <li v-for="item in arr" :key="item">{{item}}</li>
    </ul>
    <button @click="reverse">数组翻转</button>
    <button @click="slice">截取前3个</button>
    <button @click="updata">更新第一个元素值</button>
  </div>
</template>

<script>
export default {
  data(){
    return {
      arr: [5, 3, 9, 2, 1]
    }
  },
  methods: {
   reverse(){
    this.arr.reverse()
   },
   slice(){
    this.arr.slice(0,3)
    console.log(this.arr.slice(0,3));
    console.log(this.arr);
   },
   updata(){
    this.$set(this.arr,0,1000)
   }
  }
}
</script>
