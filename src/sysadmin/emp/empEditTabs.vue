<template>
  <el-tabs v-model="activeName" type="card" @tab-click="handleClick">
    <el-tab-pane label="基本信息"  name="first"><empInfo :empId="empId"></empInfo></el-tab-pane>
    <el-tab-pane label="角色信息"  name="second"><empRole :empId="empId"></empRole></el-tab-pane>
    <el-tab-pane label="岗位信息"  name="third"><empPosition :empId="empId"></empPosition></el-tab-pane>
  </el-tabs>
</template>
<script>
  import empInfo from "./empInfo"
  import empPosition from "./empPosition"
  import empRole from "./empRole"
  export default {
	components:{
		"empInfo":empInfo,
		"empPosition":empPosition,
		"empRole":empRole
	},
	props:{
		empId:String
	},
	name:'empEditTabs',
    data() {
      return {
        activeName: 'first'
      };
    },
    methods: {
      handleClick(tab, event) {
        console.log(tab, event);
      }
    },
	
  };
</script>