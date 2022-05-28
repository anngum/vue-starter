<template>
  <div id="app">
    <h1> Witaj w systemie do zapisów</h1>
   
    <div id ="form" v-if="!isLoginIn">
	
	 <login-form @login="logIn($event)"></login-form>
	 
	 <login-form @login="logIn($event)" button-label="Wejdź"></login-form>
<login-form @login="logIn($event)" button-label="Wleć"></login-form>
<login-form @login="logIn($event)" :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></login-form>

    </div>

    <div v-else="isLoginIn"><h1>Witaj {{ email }}</h1>
      <br><a href=#  @click="logOut()">Wyloguj</a>
    </div>



  </div>
</template>

<script>
import "milligram";

import LoginForm from "./LoginForm";

export default {
  components: {LoginForm},

  data() {
    return {
      email: '',
      password: '',
      isLoginIn: false,
	  buttonLabel: ''
    };
  },
  
  methods: {
    alertMyEmail() {
      alert(this.email);
    },
    logIn(username){
      this.isLoginIn = username;

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
