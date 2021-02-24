<template>
  <div>  
    <!-- <app-header v-bind:프롭스 속성 이름="상위 컴포넌트 데이터 이름"></app-header> -->
    <app-header
     v-bind:propsdata="headerName"
     v-on:renew="renewHeaderName"
    ></app-header>
    <app-footer></app-footer>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue'
import AppFooter from './components/AppFooter.vue'

export default {
  data: function(){
    return {
      headerName: 'HEADER'
    }
  },
  components: {
    'app-header': AppHeader,
    'app-footer': AppFooter
  },
  methods: {
    renewHeaderName: function(){
      this.headerName = "hi";
    }
  }
}
</script>

<style>
</style>
