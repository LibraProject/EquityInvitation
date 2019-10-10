<template>
  <div>
    <el-form :label-position="labelPosition" label-width="200px" :model="formLabelAlign">
      <div class="da">
        <el-form-item label="姓名">
          <el-input v-model="formLabelAlign.name"></el-input>
        </el-form-item>
        <el-form-item label="课程次数">
          <el-input v-model="formLabelAlign.region"></el-input>-
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


    <el-table :data="tableData" border style="1000" fit align="center">
      <el-table-column v-for="(item,index) in arr" :key="index" :prop="item.prop" :label="item.label" :width="item.width" :fixed="item.position" sort></el-table-column>
      <el-table-column fixed="right" label="操作" width="100">
        <template slot-scope="scope">
          <el-button @click="handleClick(scope.row)" type="text" size="small">查看</el-button>
          <el-button type="text" size="small">编辑</el-button>
        </template>
      </el-table-column>
    </el-table>

    <el-pagination  background  layout="prev, pager, next"  :total="1000"></el-pagination>
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
      arr: [
            { label: "姓名", prop: 'name', position: 'fixed', width: 150,sort:true },
            { label: "所在机构", prop: 'institution', position: null, width: 150,sort:false },
            { label: "是否Alpha律所", prop: 'isAlphaLaw', position: null, width: 150,sort:false },
            { label: "职务", prop: 'duty', position: null, width: 150,sort:false },
            { label: "执业年限", prop: 'practiceYear', position: null, width: 150,sort:false },
            { label: "手机号", prop: 'cellPhone', position: null, width: 150,sort:false },
            { label: "最后更新时间", prop: 'LastUpdateTime', position: null, width: 150,sort:false },
            { label: "区域", prop: 'area', position: null, width: 150,sort:false },
            { label: "邀请状态", prop: 'invite', position: null, width: 150,sort:false },
            { label: "邀请人", prop: 'invitePeople', position: null, width: 150,sort:false },
            { label: "邀请记录", prop: 'inviteRecord', position: null, width: 150,sort:false },
            { label: "计划跟进日期", prop: 'practiceYears', position: null, width: 150,sort:false },
            { label: "执业年限", prop: 'plannedFollow', position: null, width: 150,sort:false },
            { label: "Alpha用户最近登录时间", prop: 'AlphhaUserLoginTime', position: null, width: 150,sort:false },
            { label: "近一个月的使用次数", prop: 'NearlyMonthUse', position: null, width: 150,sort:false },
            { label: "iCourt学员", prop: 'iCourtStudent', position: null, width: 150,sort:false },
            { label: "参加课程次数", prop: 'courseCount', position: null, width: 150,sort:false },
            { label: "是否上法学员", prop: 'isLawStudent', position: null, width: 150,sort:false },
            { label: "美国行学员", prop: 'usastudent', position: null, width: 150,sort:false },
            { label: "是否未来律所", prop: 'lastLaw', position: null, width: 150,sort:false },
            { label: "标签", prop: 'tag', position: null, width: 150,sort:false },
            { label: "邀请级别", prop: 'inviteLevel', position: null, width: 150,sort:false },
            { label: "决策点", prop: 'decision', position: null, width: 150,sort:false },
            { label: "Alpha用橙子手机户", prop: 'AlphaOrangePhoneUser', position: null, width: 150,sort:false },
            { label: "Alpha用户数", prop: 'AlphaUsercount', position: null, width: 150,sort:false },
            { label: "出生日期", prop: 'birthday', position: null, width: 150,sort:false },
            { label: "最后联系时间", prop: 'lastRelationTime', position: null, width: 150,sort:false }
        ],
      tableData: [
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},
        {name:"王小虎",institution:"北京市清华源律师事务所",isAlphaLaw:"是",duty:"主任",practiceYear:"3年",cellPhone:"138****2468",LastUpdateTime:new Date().toLocaleDateString(),area:"北京市海淀区",invite:"A+ 联系企业家中",invitePeople:"王储",inviteRecord:'',practiceYears:'',plannedFollow:"1年",AlphhaUserLoginTime:"2019-10-1",NearlyMonthUse:9,iCourtStudent:'是',courseCount:"否",isLawStudent:"否",usastudent:"否",lastLaw:"否",tag:"隐藏",inviteLevel:"一级",decision:'',AlphaOrangePhoneUser:"是",AlphaUsercount:0,birthday:"2000-10-1",lastRelationTime:new Date().toLocaleDateString()},

      ]
    };
  },
  methods: {
    handleClick(row) {
      console.log(row);
    }
  }
};
</script>
<style>
.app-main {
  padding: 30px;
}
.da {
  width: 20%;
}
.el-form--label-right {
  display: flex;
  justify-content: space-evenly;
}
.el-form-item__content {
  display: flex;
}
.el-form-item {
  margin-bottom: 7px;
}
.el-table {
  margin: 0 auto;
}
</style>