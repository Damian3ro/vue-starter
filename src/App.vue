<template>
  <div class="my-app">
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <div v-if="loggedIn">
      <h2>Witaj {{ email }}</h2>
<!--      <button @click="logOut()">Wyloguj</button>-->
      <a @click="logOut()">Wyloguj</a>
    </div>
    <div v-else>
        <div v-if="!email.includes('@')">W adresie brakuje znaku @ !</div>
        <div>Zaloguj się e-mailem
          <input type="email" v-model="email">
          <button @click="logIn()">Wchodzę</button>
        </div>
    </div>

<!--    <div v-if="!email.includes('@')">W adresie brakuje znaku @ !</div>-->
<!--    <div v-else-if="email.length < 10">Ale masz krótki adres! Twój adres ma {{ email.length }} znaki.</div>-->
<!--    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz - ma {{ email.length }} znaki.</div>-->
<!--    <div v-else>Twój adres e-mail jest stanowczo za długi - ma {{ email.length }} znaki.</div>-->
  </div>
</template>

<script>
import "milligram";

export default {
  data() {
    return {
      email: 'dstasik@student.agh.edu.pl',
      password: '',
      loggedIn: false
    };
  },
  methods: {
    logIn() {
      this.loggedIn = true;
    },
    logOut() {
      this.loggedIn = false;
    },
    alertMyEmail() {
      alert(this.email);
    }
  }
}
</script>

<style>
.my-app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
}
</style>
