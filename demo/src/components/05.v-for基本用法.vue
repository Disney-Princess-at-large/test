<template>
  <div id="app">
    <div id="app">
    <!-- 语法1:
      v-for="(值变量名, 索引变量名) in 目标结构"
      口诀: 想要谁循环就放到谁身上
     -->
      <ul>
        <li v-for="(item, index) in arr" :key="item">
          {{ index }} - {{ item }}
        </li>
      </ul>

      <ul>
        <li v-for="obj in stuArr" :key="obj.id">
          <span>{{obj.name}}</span>
          <span>{{obj.sex}}</span>
          <span>{{obj.hobby}}</span>
        </li>
      </ul>

      <!-- v-for遍历对象(了解) -->
      <div v-for="(value, key) in tObj" :key="value">
        {{key}} -- {{value}}
      </div>
       <br>
      <!-- v-for遍历整数(了解) - 从1开始 -->
      <div v-for="item in count" :key="item">{{item}}</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: ["小明", "小欢欢", "大黄"],
      stuArr: [
        {
          id: 1001,
          name: "孙悟空",
          sex: "男",
          hobby: "吃桃子",
        },
        {
          id: 1002,
          name: "猪八戒",
          sex: "男",
          hobby: "背媳妇",
        },
      ],
      tObj: {
        name: "小黑",
        age: 18,
        class: "1期",
      },
      count: 10,
    };
  },
};
</script>
