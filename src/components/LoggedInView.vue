<template>
  <div>
    <h2>Witaj {{ userEmail }}</h2>
    <button @click="click()">Wyloguj</button>
  </div>
</template>

<script>
export default {
  props: ['userEmail'],

  data() {
    return {
      userEmail: this.userEmail
    }
  },

  methods: {
    click() {
      this.$emit('logout', { isLoggedIn: false } );
    }
  },
}
</script>