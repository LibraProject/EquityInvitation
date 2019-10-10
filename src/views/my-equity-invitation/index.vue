<template>
  <div class="wrap">
    <el-form ref="form" :model="form">
      <el-row v-for="(item, index) in filterParams" :key="index" type="flex">
        <el-col v-for="(value, key) in item" :key="key" :span="6" class="form-item">
          <el-form-item :label="value.label" class="form-label">
            <component :is="value.is" v-model="form[value.name]" :placeholder="value.placeholder" :range.sync="form[value.name]" :picker-options="form.pickerOptions1">
              <el-option v-for="(v, k) in value.list" :key="k" :label="v.label" :value="v.value" />
            </component>
          </el-form-item>
        </el-col>
      </el-row>
      <el-form-item>
        <div class="left">
          <el-button type="primary" @click="open">+新增客户</el-button>
          <el-button type="primary">今日跟进</el-button>
        </div>
        <div class="right">
          <el-button type="primary" @click="submit">搜索</el-button>
          <el-button type="primary" @click="reset">重置</el-button>
        </div>
      </el-form-item>
    </el-form>
    <NewCustomer v-show="isShow" @showChange="showChanges" />
  </div>
</template>

<script>
import RangeInput from '@/components/Common/RangeInput'
import NewCustomer from '@/components/Common/NewCustomer'
const boolOption = [{ label: '是', value: true }, { label: '否', value: false }]
const intentLevel = [{ label: '无', value: '无' }, { label: 'A', value: 'A' }, { label: 'B', value: 'B' }, { label: 'C', value: 'C' }, { label: 'D', value: 'D' }]
const inviteStatus = [{ 'label': '已添加' }, { 'label': '已邀请' }, { 'label': '已同意' }, { 'label': '已拒绝' }, { 'label': '已确认' }, { 'label': '已参加' }, { 'label': '未参加' }]

export default {
  name: 'Guide',
  components: {
    RangeInput,
    NewCustomer
  },
  data() {
    return {
      isShow: false,
      filterParams: [],
      form: {
        name: '',
        institution: '',
        phone: '',
        position: '',
        range: [],
        isAlphaUser: '',
        isIcourtStudent: '',
        subject: '',
        subName: '',
        province: '',
        city: '',
        area: '',
        tags: '',
        exclude: '',
        inviteStatus: '',
        inviter: '',
        screen: '',
        content: '',
        endTime: '',
        inviteLevel: '',
        orangePhone: '',
        chatGroup: '',
        remark: '',
        ageLimit: [],
        birthDay: '',
        active: '',
        activeType: '',
        sign: '',
        takeTime: '',
        isOrNot: '',
        types: '',
        activityId: '',
        latelyTime: '',
        follow: '',
        followTime: '',
        numberUse: '',
        upDataTime: '',
        pickerOptions1: {
          disabledDate(time) {
            return time.getTime() > Date.now()
          },
          shortcuts: [{
            text: '今天',
            onClick(picker) {
              picker.$emit('pick', new Date())
            }
          }, {
            text: '昨天',
            onClick(picker) {
              const date = new Date()
              date.setTime(date.getTime() - 3600 * 1000 * 24)
              picker.$emit('pick', date)
            }
          }, {
            text: '一周前',
            onClick(picker) {
              const date = new Date()
              date.setTime(date.getTime() - 3600 * 1000 * 24 * 7)
              picker.$emit('pick', date)
            }
          }]
        }
      }
    }
  },
  mounted() {
    this.initFilterParams()
  },
  methods: {
    submit() {
      console.log('form...', this.$refs.form.model)
    },
    reset() {
      console.log(this.$refs.form.resetFields)
      this.$refs.form.resetFields()
    },
    open() {
      this.isShow = !this.isShow
    },
    showChanges() {
      this.isShow = false
    },
    initFilterParams() {
      this.filterParams = [
        [
          { label: '姓名', name: 'name', is: 'el-input', placeholder: '请输入姓名' },
          { label: '所在机构', name: 'institution', is: 'el-input', placeholder: '请输入所在机构' },
          { label: '手机号', name: 'phone', is: 'el-input', placeholder: '请输入手机号' },
          { label: '职务', name: 'position', is: 'el-select', list: [], placeholder: '请选择职务' }
        ],
        [
          { label: '课程次数', name: 'range', is: 'range-input' },
          { label: '是否Alpha用户', name: 'isAlphaUser', is: 'el-select', list: boolOption, placeholder: '请选择Alpha用户' },
          { label: '是否iCourt学员', name: 'isIcourtStudent', is: 'el-select', list: boolOption, placeholder: '请选择iCourt学员' },
          { label: '上过的课程', name: 'subject', is: 'el-select', list: [], placeholder: '请选择上过的课程' }
        ],
        [
          { label: '课程名称', name: 'subName', is: 'el-input', placeholder: '请选择课程名称' },
          { label: '所在省份', name: 'province', is: 'el-select', list: [], placeholder: '请选择所在省份' },
          { label: '所在城市', name: 'city', is: 'el-select', list: [], placeholder: '请选择所在城市' },
          { label: '所在区县', name: 'area', is: 'el-select', list: [], placeholder: '请选择所在区县' }
        ],
        [
          { label: '标签', name: 'tags', is: 'el-select', list: [], placeholder: '请选择标签' },
          { label: '是否为排除标签中所选中', name: 'exclude', is: 'el-select', list: boolOption, placeholder: '请选择是否为排除标签中所选中' },
          { label: '邀请状态', name: 'inviteStatus', is: 'el-select', list: [], placeholder: '请选择邀请状态' },
          { label: '邀请人', name: 'inviter', is: 'el-select', list: [], placeholder: '请选择邀请人' }
        ],
        [
          { label: '邀请时间筛选', name: 'screen', is: 'el-date-picker', placeholder: '请选择邀请时间筛选' },
          { label: '跟进记录', name: 'content', is: 'el-input', placeholder: '请输入跟进记录' },
          { label: '最后联系时间', name: 'endTime', is: 'el-date-picker', placeholder: '请选择最后联系时间' },
          { label: '邀请级别', name: 'inviteLevel', is: 'el-select', list: intentLevel, placeholder: '请选择邀请级别' }
        ],
        [
          { label: '橙子手机', name: 'orangePhone', is: 'el-input', placeholder: '请输入橙子手机' },
          { label: '所在群', name: 'chatGroup', is: 'el-input', placeholder: '请输入所在群' },
          { label: '备注', name: 'remark', is: 'el-input', placeholder: '请输入备注' },
          { label: '执业年限', name: 'ageLimit', is: 'range-input' }
        ],
        [
          { label: '出生日期', name: 'birthDay', is: 'el-date-picker', placeholder: '请选择出生日期' },
          { label: '是否参加活动', name: 'active', is: 'el-select', list: boolOption, placeholder: '请选择是否参加活动' },
          { label: '活动类型', name: 'activeType', is: 'el-date-picker', list: [], placeholder: '请选择活动类型' },
          { label: '是否签到', name: 'sign', is: 'el-select', list: boolOption, placeholder: '请选择是否签到' }
        ],
        [
          { label: '参加时间', name: 'takeTime', is: 'el-select', list: [], placeholder: '请选择参加时间' },
          { label: '是否购买该产品', name: 'isOrNot', is: 'el-select', list: boolOption, placeholder: '请选择是否购买该产品' },
          { label: '产品类型', name: 'types', is: 'el-select', list: [], placeholder: '请选择产品类型' },
          { label: '产品名称', name: 'activityId', is: 'el-select', list: [], placeholder: '请选择产品名称' }
        ],
        [
          { label: '最近一次登录时间', name: 'latelyTime', is: 'el-date-picker', placeholder: '请选择最近一次登录时间' },
          { label: '跟进人', name: 'follow', is: 'el-select', list: [], placeholder: '请选择跟进人' },
          { label: '计划跟进日期', name: 'followTime', is: 'el-date-picker', placeholder: '请选择计划跟进日期' },
          { label: '近一个月使用次数', name: 'numberUse', is: 'el-select', list: [], placeholder: '请选择近一个月使用次数' }
        ],
        [
          { label: '新增邀请日期', name: 'upDataTime', is: 'el-date-picker', placeholder: '请选择新增邀请日期' }
        ]
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
  .wrap {
    width: 100%;
    height: 100%;
    padding: 15px;
  }
  .form-item /deep/ .el-form-item{
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    margin-bottom: 10px;
  }
  .form-label /deep/ .el-form-item__label{
    text-align: left;
    font-size: 12px;
    width: 100% !important;
  }
  .el-date-editor.el-input{
    width: 200px;
  }
  .left{
    float: left;
  }
  .right{
    float: right;
  }
</style>
