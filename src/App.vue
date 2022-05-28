<template>
  <div>
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <div v-if="!isAuthenticated">
      <login-form @login="logIn($event)" button-label="Wejdź"></login-form>
      <login-form @login="logIn($event)" button-label="Wleć"></login-form>
      <login-form @login="logIn($event)" :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></login-form>
    </div>
    <div v-else>
      <h2>Witaj {{email}}</h2>
      <a @click="logOut()">Wyloguj</a>
    </div>
  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
export default {
    components: {LoginForm},
    data(){
        return{
          email: '',
          isAuthenticated: false,
        };
    },
    methods: {
      logIn() {
        this.isAuthenticated = true;
      },
      logOut() {
        this.isAuthenticated = false;
      },
    },
}
</script>

<style>

</style>
