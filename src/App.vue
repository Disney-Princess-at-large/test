<template>
  <div id="app">
    <div>
      <span>姓名:</span>
      <input type="text" v-model="name" />
    </div>
    <div>
      <span>年龄:</span>
      <input type="number" v-model="age" />
    </div>
    <div>
      <span>性别:</span>
      <select v-model="sex">
        <option value="男">男</option>
        <option value="女">女</option>
      </select>
    </div>
    <div>
      <button @click.prevent="addFn">添加/修改</button>
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
        <tr v-for="obj in list" :key="obj.id">
          <td>{{ obj.id }}</td>
          <td>{{ obj.name }}</td>
          <td>{{ obj.age }}</td>
          <td>{{ obj.sex }}</td>
          <td>
            <button @click="delFn(obj.id)">删除</button>
            <button @click="editFn(obj.id)">编辑</button>
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
      list: [],
      name: "",
      age: 0,
      sex: "",
    };
  },
  methods: {
    addFn() {
      if (this.name.trim() === "" || this.age === 0)
        return alert("请输入完整的信息");
      const id = this.list[this.list.length - 1]
        ? this.list[this.list.length - 1].id + 1
        : 1;
      this.list.push({
        id,
        name: this.name,
        age: this.age,
        sex: this.sex,
      });
      this.name = "";
      this.age = 0;
    },
    delFn(id) {
      let index = this.list.findIndex((obj) => obj.id === id);
      this.list.splice(index, 1);
    },
    editFn(id) {
      let index = this.list.findIndex((obj) => obj.id === id);

      this.list[index].name = this.name;
      this.list[index].age = this.age;
      this.list[index].age = this.sex;
    },
  },
};
</script>
