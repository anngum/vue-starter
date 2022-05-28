<template>
  <div id="app">
    <h1> Witaj w systemie do zapisów</h1>
   
    <div id ="form" v-if="!authUser">
	
	 <login-form @login="logIn($event)"></login-form>
	 
	 <login-form @login="logIn($event)" button-label="Wejdź"></login-form>
<login-form @login="logIn($event)" button-label="Wleć"></login-form>
<login-form @login="logIn($event)" :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></login-form>

    </div>

    <div v-else="authUser">
	
	<is-login @logout="logOut()" :username="authUser"></is-login>
    </div>



  </div>
</template>

<script>
import "milligram";

import LoginForm from "./LoginForm";
import IsLogin from "./IsLogin";

export default {
  components: {LoginForm, IsLogin},

  data() {
    return {
      email: '',
      password: '',
      authUser: false,
	  buttonLabel: ''
    };
  },
  
  methods: {
    alertMyEmail() {
      alert(this.email);
    },
    logIn(username){
      this.authUser = username;

    },
    logOut(){
      this.authUser = false;
      this.email = '';

    }
  }
}
</script>

<style>

</style>
