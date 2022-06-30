<template>
  <div>
    <p>请选择你要购买的书籍</p>
    <ul>
        <li v-for="(item,num) in arr" :key="num">
            <span>{{item.name}}</span>
            <button @click="addFn(num)">买书</button>
        </li>
    </ul>
    <table border="1" width="500" cellspacing="0">
      <tr>
        <th>序号</th>
        <th>书名</th>
        <th>单价</th>
        <th>数量</th>
        <th>合计</th>
      </tr>
      <tr v-for="(item,index) in arr" :key="index">
        <td>{{index+1}}</td>
        <td>{{item.name}}</td>
        <td>{{item.price}}</td>
        <td>{{item.count}}</td>
        <td>{{item['price'] * item['count']}}</td>
      </tr>
    </table>
    <p>总价格为:{{allPrice}} </p>
  </div>
</template>

<script>
export default {
    name:"FourTest",
    data() {
        return {
        arr: [
            {
            name: "水浒传",
            price: 100,
            count: 0,
            },
            {
            name: "西游记",
            price: 150,
            count: 0,
            },
            {
            name: "三国演义",
            price: 200,
            count: 0,
            },
            {
            name: "红楼梦",
            price: 100,
            count: 0,
            },
        ],
        };
    },
    methods: {
        addFn(num){
            this.arr[num].count ++;
        }
    },
    computed:{
        allPrice(){
            return this.arr.reduce((pre,cur) => {
                return (pre += cur.count * cur.price)
            },0)
        }
    }
};
</script>