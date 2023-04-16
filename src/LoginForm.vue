<template>
  <div>
    <label>Zaloguj się e-mailem</label>
    <input type="email" v-model="email">
    <button @click="enter()">{{ buttonLabel }}</button>

<!--    <div v-if="!email.includes('@')">W adresie brakuje znaku @ !</div>-->
<!--    <div v-if="email.length < 10">Ale masz krótki adres! Twój adres ma {{ email.length }} znaki.</div>-->
<!--    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz - ma {{ email.length }} znaki.</div>-->
<!--    <div v-else>Twój adres e-mail jest stanowczo za długi - ma {{ email.length }} znaki.</div>-->
  </div>
</template>

<script>
export default {
  props: {
    buttonLabel: String
  },
  data() {
    return {
      email: ''
    }
  },
  methods: {
    enter() {
      this.$emit('login', this.email);
    }
  }
}
</script>

<style scoped>

</style>