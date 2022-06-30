<template>
  <div>
    <ul>
      <li v-for="item in myArr" :key="item">{{ item }}</li>
      <button @click="btn">点我前进</button>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      myArr: ["帅哥", "美女", "程序猿"],
    }
  },
  methods: {
    btn(){
      this.myArr.push(this.myArr[0])
      this.myArr.shift()
    }
  },
}
</script>

<style>

</style>