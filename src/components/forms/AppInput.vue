<template>
  <div class="form-group">
    <label :for="nome">{{ label }}</label>
    <input type="text" :name="nome" v-model="modelData" class="form-control form-control-sm"
      :class="errors ? 'is-invalid' : ''">
    <span v-if="errors" class="invalid-feedback">
      {{ errors }}
    </span>
  </div>
</template>

<script>
export default {
  name: "AppInput",
  props: {
    label: {
      type: String,
      required: true
    },
    errors: {
      type: String
    },
    nome: {
      type: String,
      required: false
    },

    placeholder: {
      type: String,
      required: false,
      default: ''
    },
  },
  computed: {
    modelData: {
      get () {
        return this.value;
      },
      set (value) {
        this.$emit('input', value);
      }
    }
  },
}
</script>

<style scoped>

</style>
