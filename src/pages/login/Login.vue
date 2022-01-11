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

export default {
  name: "Login",
  data() {
    return {
      user: {}
    }
  },
  created() {
    let user = sessionStorage.getItem('user')
    if (user) {
      this.$router.push('/')
    }
  },
  methods: {
    logar() {
      this.$http.post('/login', this.user)
        .then((result) => {
          let user = result.data
          if (user && user.access_token) {
            sessionStorage.setItem('user', JSON.stringify(user))
            this.$router.push('/')
            return;
          }
          alert('Login inválido')
        })
        .catch((errors) => console.log(errors))


    }
  }
}
</script>

<style scoped>

</style>
