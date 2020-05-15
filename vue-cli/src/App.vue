<template>
  <div>
    <!-- <app-header
     v-bind:프롭스 속성 이름="상위 컴포넌트 데이터 이름" 
     v-on:하위컴포넌트에서 올라온 이벤트 이름="실행할 메서드"
     ></app-header> -->
    <app-header 
    v-bind:propsdata="str" 
    v-on:renew="renewStr"
    ></app-header>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue'

export default {
  data(){
    return {
      str : 'Header'
    }
  },
  components:{
    'app-header' : AppHeader
  },
  methods:{
    renewStr(){
      this.str = 'alex'
    }
  }
}
</script>

<style>

</style>