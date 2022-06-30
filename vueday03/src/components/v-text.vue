<template>
  <div>
    <p v-text="str"></p>
    <p v-html="str"></p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      str:'<span>我是span标签</span>'
    }
  },
}
</script>

<style>

</style>