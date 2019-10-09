<template>
  <el-form
    :model="ruleForm"
    :rules="rules"
    ref="ruleForm"
    label-width="100px"
    class="demo-ruleForm"
  >
    <el-form-item label="活动名称" prop="name">
      <el-input v-model="ruleForm.name"></el-input>
    </el-form-item>
    <el-form-item label="活动名称" prop="name">
      <el-date-picker v-model="ruleForm.name"></el-date-picker>
    </el-form-item>
    <el-form-item v-for="(ele,index) in fromArr" :key="index">
    
      {{`<${ele.type}></${ele.type}>`}}
    </el-form-item>
  </el-form>
</template>

<script>
import fromArr from './from'
export default {
  data() {
    return {
      ruleForm: {
        name: ""
      }
    };
  },
  methods: {
    submitForm(formName) {
      this.$refs[formName].validate(valid => {
        if (valid) {
          alert("submit!");
        } else {
          console.log("error submit!!");
          return false;
        }
      });
    },
    resetForm(formName) {
      this.$refs[formName].resetFields();
    }
  }
};
</script>
