<template>
  <div class="modal" tabindex="-1" :id="identificador">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title">{{ titulo }}</h5>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body">
          <slot></slot>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  props: ['identificador', 'titulo']
}
</script>

<style scoped>

</style>
