<template>
  <div>
    <ul>
      <li v-if="age >= 18">成年人</li>
      <li v-else-if="age < 18 && age >= 12">青少年</li>
      <li v-else>小孩</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      age:20
    }
  },
}
</script>

<style>

</style>
