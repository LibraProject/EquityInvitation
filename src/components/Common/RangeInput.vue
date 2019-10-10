<template>
  <div>
    <el-input v-model="range[0]" width="82" placeholder="最小" type="number"></el-input>
    -
    <el-input v-model="range[1]" width="82" placeholder="最大" type="number"></el-input>
  </div>
</template>

<script>
export default {
  props: ['range']
}
</script>
<style scoped>

</style>