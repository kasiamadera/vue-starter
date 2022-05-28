<template>
  <div>
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <div v-if="!isAuthenticated">
      Zaloguj się e-mailem
      <input type="text" v-model="email">
      <button @click="logIn()">Wchodzę</button>
    </div>
    <div v-else>
      <h2>Witaj {{email}}</h2>
      <a @click="logOut()">Wyloguj</a>
    </div>
  </div>
</template>

<script>
import "milligram";
export default {
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
