<!-- - 需求1: 铺设页面, 准备初始的数据(自己手写数据结构) - 前面是数组索引+1 *作为序号
- 需求2: 当输入框没有值, 要给用户一个提示, 必须都有值才能增加新数据 (数据驱动页面哦)
- 需求3: 添加功能 - 想好数据结构统一对象的key
- 需求4: 点击编辑功能, 把值赋予到输入框上(不要操作dom, 数据驱动页面)
- 需求5: 用户修改后, 点击相同按钮 - 想想怎么判断怎么是添加还是修改的功能 (提示: 准备一个全局变量, 点过编辑按钮可以让它为true) - 实现编辑后更新页面效果
- 需求6: 点击删除, 删除这行数据 -->
<template>
  <div id="app">
    <div>
      <span>姓名:</span>
      <input type="text" v-model.trim="name" />
    </div>
    <div>
      <span>年龄:</span>
      <input type="number" v-model.number="age" />
    </div>
    <div>
      <span>性别:</span>
      <select v-model="sex">
        <option value="男">男</option>
        <option value="女">女</option>
      </select>
    </div>
    <div>
      <button @click="addFn">添加/修改</button>
    </div>
    <div>
      <table border="1" cellpadding="10" cellspacing="0">
        <tr>
          <th>序号</th>
          <th>姓名</th>
          <th>年龄</th>
          <th>性别</th>
          <th>操作</th>
        </tr>
        <tr v-for="item in arr" :key="item.id">
          <td>{{ item.id }}</td>
          <td>{{ item.name }}</td>
          <td>{{ item.age }}</td>
          <td>{{ item.sex }}</td>
          <td>
            <button @click="delFn(item.id)">删除</button>
            <button @click="editFn(item.id)">编辑</button>
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      id:'',
      arr: [],
      name: '',
      age: '',
      sex: '男',
      flag :true
    }
  },
  methods: {
    addFn() {
      if (this.flag) {
        if (this.name === '' || this.age === '') {
          this.name = ''
          this.age = ''
          return alert('Please enter age and name')
        }
        this.arr.push({
          id: this.arr.length + 1,
          name: this.name,
          age: this.age,
          sex: this.sex,
        })
        this.name = ''
        this.age = ''
      }else{
        this.arr[this.id-1].name = this.name
        this.arr[this.id-1].age = this.age
        this.arr[this.id-1].sex = this.sex
        this.name = ''
        this.age = ''
        this.flag = true

      }
    },
    editFn(id) {
      this.flag = false
      if (!this.flag) {
        let index = this.arr.findIndex((item) => item.id === id)
        this.name = this.arr[index].name
        this.age = this.arr[index].age
        this.sex = this.arr[index].sex
        this.id = id
        // flag = true
      }
    },
    delFn(id){
      this.arr.splice(id-1,1)
    }
  },
}
</script>
