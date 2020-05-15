<template>
  <form v-on:submit.prevent="submitForm">
    <div>
      <label for="username">id : </label>
      <input type="text" id="username" v-model="username">
    </div>
    <div>
      <label for="password">pw : </label> 
      <!-- 어떤 태그를 위한 label 이냐 : for -->
      <input type="password" id="password" v-model="password">
      <!-- input id 에 label for 에 맞춰 생성해주면 둘은 한쌍이 된다. -->
    </div>
    <button type="submit">login</button>
  </form>
</template>

<script>
import axios from 'axios';

export default {
  data(){
    return {
      username:'',
      password:''
    }
  },
  methods:{
    submitForm(){
      // v-on click 을 해도 되겠지만, form 에 submit 이 실행 될 것

      // .post 데이터를 생성하거나 조작할때 
      var url = 'https://jsonplaceholder.typicode.com/users'
      var data = {
        username: this.username,
        password: this.password
      }
      // axios.post(url, data); 
      axios.post(url, data)
      .then(res=>{
        console.log(res);
        
      })
      .catch(error=>{
        console.log(error);
        
      })
      
    }
  }
}
</script>

<style>

</style>