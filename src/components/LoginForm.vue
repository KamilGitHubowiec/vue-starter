<template>
  <form @submit="enter()">
    <label>Zaloguj się e-mailem</label>
    <input type="email" v-model="email">
    <button type="submit">{{ buttonLabelToDisplay }}</button>
    <div v-if="email.length < 10">Ale masz krótki adres!</div>
    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
    <div v-else>Za długi adres email!</div>
  </form>
</template>

<script>
export default {
  props: ['buttonLabel'],

  data() {
    return {
      email: '',
      buttonLabel: this.buttonLabel
    }
  },

  methods: {
    enter() {
      this.$emit('login', this.email);
    }
  },

  // mounted() {
  //   if (!this.buttonLabel) {
  //     this.buttonLabel = 'Zaloguj się';
  //   }
  // },

  computed: {
    buttonLabelToDisplay() {
      return this.buttonLabel || 'Zaloguj się';  
    }
  }
}
</script>