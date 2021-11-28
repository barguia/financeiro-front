<template>
  <div>
    <button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#modal-login">
      Login
    </button>

    <modal identificador="modal-login" titulo="Login">
      <div class="form-group">
        <label for="email">E-mail</label>
        <input type="email" class="form-control" name="email" id="email">
      </div>
      <div class="form-group">
        <label for="email">Senha</label>
        <input type="password" class="form-control" name="senha" id="senha">
      </div>
      <button class="btn btn-primary">Logar</button>
    </modal>
  </div>
</template>

<script>
import Modal from '@/components/Modal'
export default {
  name: "Login",
  components: {
    Modal
  }
}
</script>

<style scoped>

</style>
