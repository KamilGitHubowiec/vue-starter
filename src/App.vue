<template>
  <div>
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <login-form v-if="isLoggedIn === false" @login="logUserIn($event)" button-label="Wejdź"></login-form>
    <login-form v-if="isLoggedIn === false" @login="logUserIn($event)" button-label="Wleć"></login-form>
    <login-form v-if="isLoggedIn === false" @login="logUserIn($event)" :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></login-form>
    <div v-if="isLoggedIn === true">
      <h2>Witaj {{ email }}</h2>
      <button @click="logUserOut()">Wyloguj</button>
    </div>
  </div>
</template>

<script>
import "milligram";
import LoginForm from "./components/LoginForm";

export default {
  components: {
    LoginForm
  },

  data() {
    return {
      email: '',
      isLoggedIn: false
    }  
  },

  methods: {
    logUserIn(email) {
      this.email = email,
      this.isLoggedIn = true
    },
    logUserOut() {
      this.email = '',
      this.isLoggedIn = false
    }
  }
}
</script>

<style>
</style>
