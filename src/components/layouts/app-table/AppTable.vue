<template>
  <span>
    <table class="table table-sm table-striped" v-if="table.body.length > 0">
      <thead>
      <tr class="text-center">
        <td v-for="col in table.cols">{{ col.title }}</td>
      </tr>
      </thead>
      <tbody>
        <tr v-for="row in table.body">
          <td>{{ row.value }}</td>
        </tr>
      </tbody>
    </table>
    <p class="alert alert-warning" v-else>{{ emptyMessage }}</p>
  </span>
</template>

<script>
export default {
  name: "AppTable",
  props: ['table', 'emptyMessage']
}
</script>

<style scoped>

</style>
