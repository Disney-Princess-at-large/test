<template>
    <div>
        <div>
            <ul>
                <li v-for="(item,index) in arr" :key="item">
                    <span>{{item}}</span>
                    <button @click="delFn(index)">删除</button>
                </li>                
            </ul>
            <button @click="addFn">生成</button>
        </div>
    </div>
</template>

<script>
    export default {
        name:"TwoTest",
        data(){
            return{
                arr:[3,4,5]
            }
        },
        methods: {
            addFn(){
                this.arr.push(Math.floor(Math.random() * 18));
            },
            delFn(index){
                this.arr.splice(index, 1);
            }
        },
    }
</script>

<style>

</style>