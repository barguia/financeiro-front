<template>
  <div id="app">
    <header>
      <cabecalho></cabecalho>
    </header>

    <main class="container-fluid">
      <router-view/>
    </main>
  </div>
</template>

<script>
import Cabecalho from "@/components/layouts/Cabecalho";

export default {
  name: 'App',
  components: {
    Cabecalho
  }
}
</script>

<style>

</style>
