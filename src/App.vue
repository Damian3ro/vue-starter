<template>
  <div class="my-app">
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <div v-if="email">
<!--      <UserPanel @login="(username) => logIn(username)" button-label="Wejdź"></UserPanel>-->
      <h2>Witaj {{ email }}</h2>
      <a @click="logOut()">Wyloguj</a>
    </div>
    <div v-else>
      <LoginForm @login="(username) => logIn(username)" button-label="Wejdź"></LoginForm>
      <LoginForm @login="(username) => logIn(username)" button-label="Wleć"></LoginForm>
      <LoginForm @login="(username) => logIn(username)" :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></LoginForm>
    </div>
  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
//import UserPanel from "./UserPanel";

export default {
  components: {LoginForm},
  data() {
    return {
      email: '',
      password: '',
      loggedIn: false
    };
  },
  methods: {
    logIn(username) {
        //this.loggedIn = true;
        this.email = username;
    },
    logOut() {
      this.email = '';
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
