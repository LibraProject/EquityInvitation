<template>
<div>
   <el-form :label-position="labelPosition" label-width="200px" :model="formLabelAlign">
    <div class="da">
      <el-form-item label="姓名">
        <el-input v-model="formLabelAlign.name"></el-input>
      </el-form-item>
      <el-form-item label="课程次数">
        <el-input v-model="formLabelAlign.region"></el-input> - 
        <el-input v-model="formLabelAlign.region"></el-input>
      </el-form-item>
      <el-form-item label="课程名">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
      <el-form-item label="标签">
        <el-select v-model="formLabelAlign.type"></el-select>
      </el-form-item>
      <el-form-item label="邀请时间筛选">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
      <el-form-item label="橙子手机">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
      <el-form-item label="出生日期">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
      <el-form-item label="参加时间">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
      <el-form-item label="最后一次登录时间">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
      <el-form-item label="新增邀请日期">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
    </div>
     <div class="da">
      <el-form-item label="所在机构">
        <el-input v-model="formLabelAlign.name"></el-input>
      </el-form-item>
      <el-form-item label="是否Alpha用户">
        <el-input v-model="formLabelAlign.region"></el-input>
      </el-form-item>
      <el-form-item label="选择省">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
      <el-form-item label="是否为排除标签中所选">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
      <el-form-item label="跟进记录">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
      <el-form-item label="所在群">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
      <el-form-item label="是否参加活动">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
      <el-form-item label="是否购买该产品">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
      <el-form-item label="跟进人">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
    </div>
     <div class="da">
      <el-form-item label="手机号">
        <el-input v-model="formLabelAlign.name"></el-input>
      </el-form-item>
      <el-form-item label="是否iCourt学员">
        <el-input v-model="formLabelAlign.region"></el-input>
      </el-form-item>
      <el-form-item label="选择市">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
       <el-form-item label="邀请状态">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
       <el-form-item label="最后联系时间">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
       <el-form-item label="备注">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
       <el-form-item label="活动类型">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
       <el-form-item label="产品类型">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
       <el-form-item label="计划跟进日期">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
    </div>
     <div class="da">
      <el-form-item label="职务">
        <el-input v-model="formLabelAlign.name"></el-input>
      </el-form-item>
      <el-form-item label="上过的课程">
        <el-input v-model="formLabelAlign.region"></el-input>
      </el-form-item>
      <el-form-item label="选择区县">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
      <el-form-item label="邀请人">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
      <el-form-item label="邀请级别">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
      <el-form-item label="执业年限">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
      <el-form-item label="是否签到">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
      <el-form-item label="产品名称">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
      <el-form-item label="近一个月使用次数">
        <el-input v-model="formLabelAlign.type"></el-input>
      </el-form-item>
    </div>
  </el-form>
  <el-table
    :data="tableData"
    border
    style="1000">
    <el-table-column
      fixed
      prop="date"
      label="日期"
      width="150">
    </el-table-column>
    <el-table-column
      prop="name"
      label="姓名"
      width="120">
    </el-table-column>
    <el-table-column
      prop="province"
      label="省份"
      width="120">
    </el-table-column>
    <el-table-column
      prop="city"
      label="市区"
      width="120">
    </el-table-column>
    <el-table-column
      prop="address"
      label="地址"
      width="300">
    </el-table-column>
    <el-table-column
      prop="zip"
      label="邮编"
      width="120">
    </el-table-column>
    <el-table-column
      prop="zip"
      label="邮编"
      width="120">
    </el-table-column>
    <el-table-column
      prop="zip"
      label="邮编"
      width="120">
    </el-table-column>
    <el-table-column
      prop="zip"
      label="邮编"
      width="120">
    </el-table-column>
    <el-table-column
      prop="zip"
      label="邮编"
      width="120">
    </el-table-column>
    <el-table-column
      prop="zip"
      label="邮编"
      width="120">
    </el-table-column>
    <el-table-column
      prop="zip"
      label="邮编"
      width="120">
    </el-table-column>
    <el-table-column
      prop="zip"
      label="邮编"
      width="120">
    </el-table-column>
    <el-table-column
      fixed="right"
      label="操作"
      width="100">
      <template slot-scope="scope">
        <el-button @click="handleClick(scope.row)" type="text" size="small">查看</el-button>
        <el-button type="text" size="small">编辑</el-button>
      </template>
    </el-table-column>
  </el-table>
</div>
 
   
</template>

<script>
export default {
  data() {
    return {
      labelPosition: "right",
      formLabelAlign: {
        name: "",
        region: "",
        type: ""
      },
      tableData: [{
          date: '2016-05-02',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1518 弄',
          zip: 200333
        }, {
          date: '2016-05-04',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1517 弄',
          zip: 200333
        }, {
          date: '2016-05-01',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1519 弄',
          zip: 200333
        }, {
          date: '2016-05-03',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1516 弄',
          zip: 200333
        }]
    };
  },
   methods: {
      handleClick(row) {
        console.log(row);
      }
    },
};
</script>
<style>
.app-main{
  padding: 30px;
}
  .da{
    width: 20%;
  }
  .el-form--label-right{
    display: flex;
    justify-content: space-evenly;
  }
  .el-form-item__content{
    display: flex;
  }
  .el-form-item {
    margin-bottom: 7px;
}
.el-table{
  margin: 0 auto;
}
  
</style>
