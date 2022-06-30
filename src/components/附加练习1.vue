<template>
    <div>
        <div>
            <ul>
                <li v-for="(item,index) in arr" :key="index">{{item}}</li>

            </ul>
            <button @click="btn">加</button>
        </div>
    </div>
</template>

<script>
    export default {
        name:"OneTest",
        data(){
            return{
                arr:['帅锅','美铝','乔碧落']
            }
        },
        methods: {
            btn(){
                this.arr.push(this.arr[0])
                this.arr.shift()
            }
        },
    }
</script>

<style>

</style>