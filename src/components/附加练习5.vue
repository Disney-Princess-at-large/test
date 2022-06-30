<template>
    <div>
        <div v-for="(item,index) in arr" :key="index">
            <input type="checkbox" v-model="allSum" :value="item">
            <span>{{item}}</span>
        </div>
        <p>累加和：{{addSum}}</p>
    </div>
</template>

<script>
    export default {
        name:"FiveTest",
        data(){
            return{
                arr:[9, 15, 19, 25, 29, 31, 48, 57, 62, 79, 87],
                allSum:[]
            }
        },
        computed:{
            addSum(){
                return this.allSum.reduce((pre,cur) => {
                    return pre += cur
                },0)
            }
        }
    }
</script>

<style>

</style>