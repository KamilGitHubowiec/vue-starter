<template>
  <div>
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <form v-if="isLoggedIn === false" @submit="logIn()">
      <label for="email">Zaloguj się emailem</label>
      <input id="email" type="email" v-model="email">
      <button type="submit">Wchodzę</button>
      <div v-if="email.length < 10">Ale masz krótki adres!</div>
      <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
    </form>
    <div v-if="isLoggedIn === true">
      <h2>Witaj {{email}}</h2>
      <button @click="logOut()">Wyloguj</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: '',
      isLoggedIn: false
    }  
  },
  methods: {
    logIn() {
      this.isLoggedIn = true
    },
    logOut() {
      this.isLoggedIn = false,
      this.email = ''
    }
  }
}
</script>

<style>
</style>
