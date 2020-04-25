<template>
  <div>
      <h1>Witaj w systemie do zapisów na zajęcia</h1>
      <div v-if= "authenticatedUserName != ''">
          <h3>Witaj {{authenticatedUserName}}</h3>
          <a @click="logOut()">Wyloguj </a>
      </div>
      <div v-else>
          <login-form @login="logIn($event)"></login-form>
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
      email: '',
      authenticatedUserName: ''
    };
  },
  methods: {
      logIn(username) {
          this.authenticatedUserName = username;
        },
    logOut(){
        this.authenticatedUserName = '';
        this.email = '';
    }
  }
}
</script>

<style>

</style>
