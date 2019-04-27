<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>Witaj w systemie do zapisów na zajêcia</h1>
    <!-- <p>{{ email }}</p> -->
    
    <div v-if="isAuthenticated">
      Zalogowany jako {{ email }}
      <a @click="logOut()"> Wyloguj</a>
    </div>
    <div v-else>
      <login-form @login="logIn($event)"></login-form>
    </div>
    
    <!-- 
    <div v-if="email.length < 10">Ale masz krótki adres!</div>
	<div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
	<div v-else>Twój adres e-mail jest stanowczo za d³ugi.</div>
	 -->
	 
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import "milligram";
import LoginForm from "./LoginForm";

export default {
	components: {LoginForm},
	data() {
		  return {
		    email: '',
		    isAuthenticated:false
		  };
	},
	methods: {
		  alertMyEmail() {
		    alert(this.email);
		  },
		  logIn(username) {
			  this.isAuthenticated = username;
		  },
		  logOut() {
			  this.isAuthenticated = false;
			  this.email = '';
		  }
	}
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
