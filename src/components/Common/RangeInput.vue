<template>
  <div>
    <el-input v-model="range[0]" placeholder="最小" type="number" style="width:94px" />
    -
    <el-input v-model="range[1]" placeholder="最大" type="number" style="width:94px" />
  </div>
</template>

<script>
export default {
  props: ['range']
}
</script>
