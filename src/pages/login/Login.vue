<template>
  <div>
    <form @submit="logar()"></form>
    <div class="form-group">
      <label for="email">E-mail</label>
      <input type="email" class="form-control" v-model="user.email">
    </div>
    <div class="form-group">
      <label for="email">Senha</label>
      <input type="password" class="form-control" v-model="user.password">
    </div>
    <button class="btn btn-primary" @click="logar()">Logar</button>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: "Login",
  data: {
    user: {}
  },
  methods: {
    logar() {

    }
  }
}
</script>

<style scoped>

</style>
