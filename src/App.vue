<template>
  <div id="app">
    e-mail: <input type="email" v-model="email">
    <br>
    password:<input type="password" v-model="pasword">
    <h1>Twój e-mail to {{ email }}</h1>
  </div>
</template>

<script>


export default {
  data() {
    return {
      email: '',
      password: ''
    };
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
