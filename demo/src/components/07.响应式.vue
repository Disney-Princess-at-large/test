
<template>
  <div>
    <h1>{{obj.a}}</h1>
    <button @click="change">改变</button>
  </div>
</template>

<script>
export default {
data() {
  return {
    obj:{
      b:10,
      c:12
    }
  }
},
methods: {
  change(){
    this.obj={
      a:10,
      b:10,
      c:12
    }
    console.log(this.obj);
    console.log("============================");
    this.$set(this.obj,'a',10)
    console.log(this.obj);
  }
},
}
</script>

<style>

</style>
