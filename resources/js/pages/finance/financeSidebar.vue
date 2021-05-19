<template>
  <div>
    <!--只有組別-->
    <div v-for="(team,index) in teamList[`${filterYear}`]" :key="`ary${index}`" v-if="isArray==true" class="aryClass h4">{{team}}
    </div>
    <!--部+組-->
    <div v-for="(team,index) in teamList[`${filterYear}`]" :key="`obj${index}`" v-if="isArray==false" class="objClass h4">{{index}}
      <div v-for="(group,grdex) in team" :key="grdex" class="groupClass ml-3">{{group}}</div>
    </div>
  </div>
</template>
<script>
export default{
  props:['filterYear'],
  data(){
    return{
      teamList:{
          "2021":{
            "行政部":["活動組","議程組"],
            "產品部":["研發組","設計組","行銷組"],
            "商務部":["商業開發組","公關組","媒體組"],
          },
          "2022":["aa","bb","dd"]
      },
      isArray:false,
    }
  },
  watch:{
    filterYear:'currentTeamList'
  },
  methods:{
    currentTeamList:function(year){
      const vm = this;
      year = vm.filterYear;
      if(vm.teamList[year].constructor === Array){
        vm.isArray=true;
      }else{
        vm.isArray=false;
      }
    }
  },
}
</script>
<style scoped lang="scss">
.aryClass, .objClass, .groupClass{
  line-height: 2;
}
.groupClass{
  font-size: 1.2rem;
}
</style>