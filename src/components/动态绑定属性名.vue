<template>
    <div>
        <div>
            <p :style="{color:'green',fontSize:'10px'}">sufhka</p>
            <p :style="{color:currentColor,fontSize:'10px'}">fuhsak</p>
        </div>
    </div>
</template>

<script>
    export default {
        name:"VStyle",
        data(){
            return{
                currentColor: "skyblue",
            }
        }
    }
</script>

<style>

</style>