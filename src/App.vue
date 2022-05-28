<template>
  <div id="app">
    e-mail: <input type="email" v-model="email">
    <div v-if="email.length < 10">Ale masz krótki adres!</div>
    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
    <div v-else>Twój adres e-mail jest stanowczo za długi.</div>
    <button @click="alertMyEmail()">Wyświetl mój e-mail w alercie</button>
    <br>
    password:<input type="password" v-model="pasword">

    <!--  <h1>Twój e-mail to {{ email }}</h1> -->


  </div>
</template>

<script>


export default {
  data() {
    return {
      email: '',
      password: ''
    };
  },
  methods: {
    alertMyEmail() {
      alert(this.email);
    }
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
