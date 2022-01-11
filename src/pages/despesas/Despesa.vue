<template>
  <span class="row">
    <app-grid col="5" size="md" class="m-auto">
      <app-input label="Título" nome="titulo" v-model="despesa.titulo" :errors="despesa.erros"/>
      <app-input label="Valor" nome="valor" v-model="despesa.valor" :errors="despesa.erros"/>
    </app-grid>
  </span>
</template>

<script>
import AppInput from "@/components/forms/AppInput"
import AppGrid from "@/components/layouts/app-grid/AppGrid"

export default {
  name: "Despesa",
  components: {
    AppInput,
    AppGrid
  },
  data() {
    return {
      despesa: {}
    }
  }
}
</script>

<style scoped>

</style>
