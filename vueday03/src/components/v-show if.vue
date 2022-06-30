<template>
  <div>
    <p v-show="isShow">我是v-show控制的标签</p>
    <button @click="isShow = !isShow">v-show</button>
    <br>
    <p v-if="isShow1">我是v-if控制的标签</p>
    <button @click="isShow1 = !isShow1">v-if</button>

  </div>
</template>

<script>
export default {
  data() {
    return {
      isShow1:false,
      isShow:false,
    }
  },
}
</script>

<style>

</style>