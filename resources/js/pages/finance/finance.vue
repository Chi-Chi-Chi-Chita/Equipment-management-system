<template>
  <div class="container-fluid">
    <!-- memu -->
    <div class="d-flex mb-4 row align-items-center">
      <div class="col-auto btn-group btn-group-lg d-flex mr-auto">
        <button type="button" class="btn btn-primary align-self-center">請款</button>
        <button type="button" class="btn btn-primary">設定</button>
        <button type="button" class="btn btn-primary">匯出</button>
      </div>
      <form class="col-auto form-inline">
        <label class="my-1 mr-2" for="inlineFormCustomSelectPref" style="font-size:1.2rem">年份：</label>
        <select class="custom-select my-1 mr-sm-2" id="inlineFormCustomSelectPref" style="font-size:1.2rem" v-model="filter.year">
          <option :value="year" v-for="year in yearList" :key="`filter-year-${year}`">{{year}}</option>
        </select>
      </form>
    </div>
    <!--資訊欄-->
    <div class="info d-flex align-items-center justify-content-between mb-3">
      <div class="card ">
        <h4 class="card-title">己入帳贊助款</h4>
        <p class="card-text">123</p>
      </div>
      <div class="card mx-3">
        <h4 class="card-title">本年度總預算</h4>
        <p class="card-text">123</p>
      </div>
      <div class="card border-success">
        <h4 class="card-title">本年度總支出</h4>
        <p class="card-text">123</p>
      </div>
    </div>
    <!--Content-->
    <div class="row">
      <div class="col-sm-1">
        <FinanceSidebar :filterYear="filter.year" />
      </div>
      <div class="clo-sm-11">
      </div>
    </div>
  </div>
</template>

<script>
  import FinanceSidebar from "./financeSidebar"
  export default{
    components: {
      FinanceSidebar,
    },
    data(){
      return{
        yearList:['2022','2021','2019'],
        filter:{
          year:2021,
        }
      }
    },
    methods:{
      
    }
  }
</script>
<style scoped lang="scss">
  *{
    outline: 1px red dotted;
  }
  .card{
    flex:1 1 auto;
    padding:2rem;
  }
  #button-group>.btn{
    flex:0 1 auto;
  }
  .info :nth-child(1){
    border-bottom-width:1rem;
    border-color:#f0ad4e;
  }
  .info :nth-child(2){
    border-bottom-width:1rem;
    border-color:#5bc0de;
  }
  .info :nth-child(3){
    border-bottom-width:1rem;
  }
</style>