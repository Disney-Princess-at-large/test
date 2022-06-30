<!-- 目标: 点击生成按钮, 新增一个li(随机数字)和删除按钮, 点击删除按钮, 删除对应的li和值
提示: 数组渲染列表, 生成和删除都围绕数组操作 -->

<template>
  <div>
    <ul>
      <li v-for="(item, index) in arr" :key="index">
      {{ item }}
      <button @click="del(index)">删除</button></li>
      <button @click="addFn">生成</button>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [1,5,3],
    }
  },
  methods: {
    addFn(){
      let num = Math.floor(Math.random() * 9)
      this.arr.push(num)
    },
    del(index){
      this.arr.splice(index, 1)
    }
  },
}
</script>

<style>

</style>