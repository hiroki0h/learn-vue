<template>
  <!-- e.preventDefault(); -->
  <form v-on:submit.prevent="submitForm">
    <div>
      <label for="username">id:</label>
      <input type="text" id="username" v-model="username">
    </div>
    <div>
      <label for="password">password:</label>
      <input type="password" id="password" v-model="password">
    </div>
    <button type="submit">login</button>
  </form>
</template>

<script>
import axios from 'axios';

export default {
  // 값의 참조가 일어나지 않기 위에 function으로
  data: function(){
    return {
      username: '',
      password: '',
    }
  },
  methods: {
    submitForm: function(){
      console.log(this.username, this.password);
      // 브라우저에서 서버로 데이터 보내기 위해 사용
      // post - data를 생성 조작할때 사용하는 메서드
      var url = 'https://jsonplaceholder.typicode.com/users';
      var data = {
        username: this.username,
        password: this.password,
      }
      axios.post(url, data)
      .then(function(response){
        console.log(response);
      })
      .catch(function(error){
        console.log(error);
      })
    }
  }
}
</script>

<style>
div {margin-bottom: 10px;}
input {display: block;}
</style>
