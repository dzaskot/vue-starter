<template>
  <div>
      <h1>Witaj w systemie do zapisów na zajęcia</h1>
      <div v-if= "authenticatedUserName != ''">
          <h3>Witaj {{authenticatedUserName}}</h3>
          <a @click="logOut()">Wyloguj </a>
      </div>
      <div v-else>
          <label>Zaloguj się emailem </label>
          <input type="email" v-model = "email">
          <button @click="logIn()"> Zaloguj</button>
      </div>

      <!--<div v-if="email.length < 10">Ale masz krótki adres!</div>
      <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
      <div v-else>Twój adres e-mail jest stanowczo za długi.</div>

      <input type="email" v-model = "email">

      <button @click="alertMyEmail()">Wyświetl mój e-mail w alercie</button>-->
  </div>
</template>

<script>
import "milligram";
export default {
  data() {
    return {
      email: '',
      authenticatedUserName: ''
    };
  },
  methods: {
      logIn() {
          this.authenticatedUserName = this.email;
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
