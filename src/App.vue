<template>
  <div id="app">
    <h1> Witaj w systemie do zapisów</h1>
    <div id ="form" v-if="!isLoginIn">
    e-mail: <input type="email" v-model="email" >
      <!--     e-mail: <input type="email" v-model="email" @keyup.enter="alertMyEmail()"> -->
    <button @click="logIn()" >Wchodzę</button>
    </div>
   <!-- <div v-if="email.length < 10">Ale masz krótki adres!</div>
    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
    <div v-else>Twój adres e-mail jest stanowczo za długi.</div>
    <button @click="alertMyEmail()">Wyświetl mój e-mail w alercie</button>
    <br> -->
    <div v-else="isLoginIn"><h1>Witaj {{ email }}</h1>
      <br><a  @click="logOut()">Wyloguj</a>
    </div>
    
   <!-- password:<input type="password" v-model="password"> -->

    <!--  <h1>Twój e-mail to {{ email }}</h1> -->


  </div>
</template>

<script>
import "milligram";

export default {
  data() {
    return {
      email: '',
      password: '',
      isLoginIn: false
    };
  },
  methods: {
    alertMyEmail() {
      alert(this.email);
    },
    logIn(){
      this.isLoginIn = true;

    },
    logOut(){
      this.isLoginIn = false;
      this.email = '';

    }
  }
}
</script>

<style>

</style>
