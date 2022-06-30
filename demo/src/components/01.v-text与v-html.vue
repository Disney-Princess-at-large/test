<template>
  <div>
    <p v-text="str"></p>
    <p v-html="str"></p>
    <p v-html="str">{{ 10 }}</p>
    <!-- v-text把值当成普通字符串显示, v-html把值当做html解析 -->
    <!-- 注意: v-text或v-html会覆盖插值表达式 -->
    
  </div>
</template>

<script>
export default {
  data() {
    return {
      str: "<span>我是一个span标签</span>"
    }
  }
}
</script>
