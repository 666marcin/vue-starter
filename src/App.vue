<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>Witaj w systemie do zapisów na zajêcia</h1>
    <!-- <p>{{ email }}</p> -->
    
    <div v-if="isAuthenticated">
      Zalogowany jako {{ email }}
      <a @click="logOut()"> Wyloguj</a>
    </div>
    <div v-else="isAuthenticated">
      <label>Zaloguj siê e-mailem</label>
      <input type="email" v-model="email">
	  <button @click="logIn()">Wchodzê</button>
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

export default {
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
		  logIn() {
			  this.isAuthenticated = true;
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
