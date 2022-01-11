<template>
  <div>
    Bem vindo ao controle financeiro.

    <table class="table table-sm table-striped" v-if="despesas.length > 0">
      <thead>
        <tr class="text-center">
          <td>ID</td>
        </tr>
      </thead>
      <tbody>
        <tr v-for="despesa in despesas">
          <td>{{ despesa.id }}</td>
        </tr>
      </tbody>
    </table>
    <p v-else class="alert alert-warning">Não há despesas cadastradas</p>
  </div>
</template>

<script>

export default {
  name: "Home",
  data() {
    return {
      despesas: {}
    }
  },
  created() {
    let user = sessionStorage.getItem('user')
    user = JSON.parse(user)
    if (!user) {
      this.$router.push('/login')
    }

    let config = {
      headers: {'Authorization': `Bearer ${user.access_token}`}
    }
    console.log(config)
    this.$http.get('/despesas', config)
      .then((response) => {
        this.despesas = response.data
      })
    .catch((errors) => {
      console.log(errors)
    })
  }
}
</script>

<style scoped>

</style>
