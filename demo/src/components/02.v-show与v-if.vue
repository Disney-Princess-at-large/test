<template>
  <div>
    <!-- 需求：点击按钮 实现p标签 显示/隐藏动态切换
    v-show="变量/表达式"
    变量/表达式 false 的时候 标签隐藏
    变量/表达式 true  的时候 标签显示
     -->
    <p v-show="isShow">我是v-show指令</p>
    <button @click="isShow = !isShow">click me show</button>
    <br />
    <!-- v-if="变量/表达式"
    变量/表达式 false 的时候 标签隐藏
    变量/表达式 true  的时候 标签显示 -->
    <p v-if="isShow1">我是v-if指令</p>
    <button @click="isShow1 = !isShow1">click me if</button>
  </div>
</template>

<script>
export default {
data() {
    return {
      isShow: false,
      isShow1: false,
    };
  },
}
</script>

<style>

</style>
