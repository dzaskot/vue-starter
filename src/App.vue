<template>
  <div>
      <h1>Witaj w systemie do zapisów na zajęcia</h1>
      <div v-if= "authenticatedUserName != ''">
          <h3>Witaj {{authenticatedUserName}}</h3>
          <a @click="logOut()">Wyloguj </a>
      </div>
      <div v-else>
          <login-form @login="logIn($event)" button-label="Zaloguj się"></login-form>
          <login-form @login="logIn($event)" button-label="Wejdź"></login-form>
          <login-form @login="logIn($event)" button-label="Wleć"></login-form>
          <login-form @login="logIn($event)" :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></login-form>
      </div>
  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";

export default {
  components: {LoginForm},
  data() {
    return {
      authenticatedUserName: ''
    };
  },
  methods: {
      logIn(username) {
          this.authenticatedUserName = username;
        },
    logOut(){
        this.authenticatedUserName = '';
    }
  }
}
</script>

<style>

</style>
