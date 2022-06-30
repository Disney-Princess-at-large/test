<template>
  <div>
    <div>
        <!-- 需求： age 大于等于18，页面显示 成年人
         age 小于18 并且 大于等于12 ，页面显示 青少年
         age 小于12 ，页面显示 儿童 -->
            <p v-if="age >= 18">成年人</p>
            <p v-else-if="age >=12">青少年</p>
            <p v-else>儿童</p>

            <!-- v-if v-else-if v-else 配合使用 -->
 
    </div>
    <br>
    <div>
    <div>
        <!-- v-show 
        v-show ='变量/表达式'
        变量/表达式 值 为 false 的时候 隐藏dom元素
        变量/表达式 值 为 true 的时候 显示dom元素

        变量/表达式 值 false/true 都会渲染对应的dom 样式 display: none，性能更高
        频繁的切换的时候
        -->
        <p v-show="isShow">我是v-show指令</p>
        <button @click="isShow = !isShow">click me show</button>
        <br />
        <!-- v-if ='变量/表达式'
        变量/表达式 值 为 false 的时候 隐藏dom元素
        变量/表达式 值 为 true 的时候 显示dom元素 

        false 的时候 根本不会生成对应的元素
        切换的效果 根据 元素 移除/创建 

        如果一个元素一进入页面 要么显示 要么不现实，后续不会进行切换

        -->
        <p v-if="isIf">我是v-if指令</p>
        <button @click="isIf = !isIf">click me if</button>
    </div>
    </div>
    <br>
    <div>
        <h3>案例：折叠面板</h3>
        <div>
        <div class="title">
            <h4>芙蓉楼送辛渐</h4>
            <span class="btn" @click="isShow =!isShow">
            {{isShow ? "收起":"展开"}}
            </span>
        </div>
        <div class="container" v-show="isShow">
            <p>寒雨连江夜入吴,</p>
            <p>平明送客楚山孤。</p>
            <p>洛阳亲友如相问，</p>
            <p>一片冰心在玉壶。</p>
        </div>
        </div>
  </div>
  </div>
</template>

<script>
    export default {
        name:"VIf",
        data(){
            return{
                age:"19",
                isShow:false,
                isIf:false,
            }
        }
    }
</script>

<style lang="less">
body {
  background-color: #ccc;
  #app {
    width: 400px;
    margin: 20px auto;
    background-color: #fff;
    border: 4px solid blueviolet;
    border-radius: 1em;
    box-shadow: 3px 3px 3px rgba(0, 0, 0, 0.5);
    padding: 1em 2em 2em;
    h3 {
      text-align: center;
    }
    .title {
      display: flex;
      justify-content: space-between;
      align-items: center;
      border: 1px solid #ccc;
      padding: 0 1em;
    }
    .title h4 {
      line-height: 2;
      margin: 0;
    }
    .container {
      border: 1px solid #ccc;
      padding: 0 1em;
    }
    .btn {
      /* 鼠标改成手的形状 */
      cursor: pointer;
    }
  }
}
</style>