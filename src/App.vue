<template>
  <div>
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <login-form v-if="isLoggedIn === false" @login="logUserIn($event)"></login-form>
    <logged-in-view v-if="isLoggedIn === true" @logout="logUserOut($event)" :user-email="email"></logged-in-view>
  </div>
</template>

<script>
import "milligram";
import LoginForm from "./components/LoginForm";
import LoggedInView from './components/LoggedInView.vue';

export default {
  components: {
    LoginForm,
    LoggedInView
  },

  data() {
    return {
      email: '',
      isLoggedIn: false
    }  
  },

  methods: {
    logUserIn({email, isLoggedIn}) {
      this.email = email,
      this.isLoggedIn = isLoggedIn
    },
    logUserOut({isLoggedIn}) {
      this.email = '',
      this.isLoggedIn = isLoggedIn
    }
  }
}
</script>

<style>
</style>
