<template>
<form v-on:submit.prevent="submitForm">
  <div>
    <label for="email">email: </label>
    <input id="email" type="text" v-model="email">
  </div>
  <div>
    <label for="password">pw: </label>
    <input id="password" type="password" v-model="password">
  </div>
  <button type="submit">login</button>
</form>


</template>

<script>
import axios from 'axios';

export default {
  data: function() {
    return {
      email: '',
      password: ''
    }
  },
  methods:  {
    submitForm: function() {
      // event.preventDefault();
      console.log(this.email, this.password);
      var url = 'http://3.34.149.238:8080/api/basic/login';
      var data = {
        email: this.email,
        password: this.password
      }
      axios.post(url, data)
      .then(function(response) {
        console.log(response);
      })
      .catch(function(error) {
        console.log(error);
      })
    }
  }
}
</script>

<style>

</style>