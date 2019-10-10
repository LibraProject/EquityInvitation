<template>
  <div class="delige">
    <div class="mask">
      <p class="title">新增客户</p>
      <el-form ref="ruleForm" :model="ruleForm" :rules="rules" label-width="100px" class="demo-ruleForm">

        <el-form-item label="姓名" prop="name">
          <el-input v-model="ruleForm.name" />
        </el-form-item>
        <el-form-item label="性别" prop="resource">
          <el-radio-group v-model="ruleForm.resource">
            <el-radio label="男" />
            <el-radio label="女" />
          </el-radio-group>
        </el-form-item>
        <el-form-item label="职业" prop="region" class="form-label">
          <el-select v-model="ruleForm.region">
            <el-option label="区域一" value="shanghai" />
            <el-option label="区域二" value="beijing" />
          </el-select>
        </el-form-item>
        <el-form-item label="职务" prop="duty" class="form-label">
          <el-select v-model="ruleForm.duty">
            <el-option label="区域一" value="shanghai" />
            <el-option label="区域二" value="beijing" />
          </el-select>
        </el-form-item>
        <el-form-item label="所在机构" prop="institution">
          <el-input v-model="ruleForm.institution" />
        </el-form-item>
        <el-form-item label="手机" prop="phone">
          <el-input v-model="ruleForm.phone" />
        </el-form-item>
        <el-form-item label="邮箱" prop="email">
          <el-input v-model="ruleForm.email" />
        </el-form-item>
        <el-form-item label="微信" prop="weixin">
          <el-input v-model="ruleForm.weixin" />
        </el-form-item>
        <el-form-item label="执业年限" prop="year">
          <el-input v-model="ruleForm.year" />
        </el-form-item>
        <el-form-item label="客户销售人" prop="sell">
          <el-checkbox-group v-model="ruleForm.sell">
            <el-checkbox label="本人为客户销售人" name="sell" />
          </el-checkbox-group>
        </el-form-item>
      </el-form>
      <div class="btn-bottom">
        <el-button @click="resetForm">取消</el-button>
        <el-button type="primary" @click="submitForm('ruleForm')">保存</el-button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      ruleForm: {
        name: '',
        region: '',
        sell: [],
        resource: '',
        duty: '',
        institution: '',
        phone: '',
        email: '',
        weixin: '',
        year: ''
      },
      rules: {
        name: [
          { required: true, message: '请输入活动名称', trigger: 'blur' },
          { min: 3, max: 5, message: '长度在 3 到 5 个字符', trigger: 'blur' }
        ],
        institution: [
          { required: true, message: '请输入所在机构', trigger: 'blur' },
          { min: 3, max: 5, message: '长度在 3 到 5 个字符', trigger: 'blur' }
        ],
        phone: [
          { required: true, message: '请输入手机号', trigger: 'blur' },
          { min: 3, max: 5, message: '长度在 3 到 5 个字符', trigger: 'blur' }
        ],
        email: [
          { message: '请输入邮箱地址', trigger: 'blur' },
          { type: 'email', message: '请输入正确的邮箱地址', trigger: 'blur,change' }
        ],
        weixin: [
          { message: '请输入微信', trigger: 'blur' },
          { min: 3, max: 5, message: '长度在 3 到 5 个字符', trigger: 'blur' }
        ],
        year: [
          { message: '请输入执业年限', trigger: 'blur' },
          { min: 3, max: 5, message: '长度在 3 到 5 个字符', trigger: 'blur' }
        ],
        region: [
          { required: true, message: '请选择职业', trigger: 'change' }
        ],
        duty: [
          { message: '请选择职务', trigger: 'change' }
        ],
        sell: [
          { type: 'array', message: '请选择', trigger: 'change' }
        ],
        resource: [
          { message: '请选择性别', trigger: 'change' }
        ]
      }
    }
  },
  methods: {
    submitForm(formName) {
      this.$refs[formName].validate((valid) => {
        if (valid) {
          alert('submit!')
          console.log(this.ruleForm)
        } else {
          console.log('error submit!!')
          return false
        }
      })
    },
    resetForm() {
      this.$emit('showChange')
    }
  }
}
</script>

<style lang="scss" scoped>
.delige{
    width: 100%;
    height: 100%;
    position: fixed;
    left: 0;
    top: 0;
    background-color: rgba(0, 0, 0, .5);
}
.mask{
    width: 600px;
    height: 425px;
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%,-50%);
    background-color: #fff;
    border-radius: 5px;
}
.title{
    height: 40px;
    font-size: 14px;
    border-bottom: 1px solid #e9eaec;
    padding: 14px 16px;
}
.demo-ruleForm{
    display: flex;
    flex-wrap: wrap;
}
.form-label /deep/ .el-input__inner{
  width: 185px;
}
.btn-bottom{
    border-top: 1px solid #e9eaec;
    padding: 12px 18px 12px 18px;
    text-align: right;
}
</style>
