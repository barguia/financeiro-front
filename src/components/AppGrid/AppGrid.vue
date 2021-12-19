<template>
  <span :class="getClass()">
    <slot/>
  </span>
</template>

<script>
export default {
  name: 'AppGrid',
  props: ['col', 'offset', 'size'],
  methods: {
    getClass() {
      let classe = 'col';
      classe += this.col ? `-${this.size}-${this.col}` : '';
      classe = this.offset ? ` col-${this.size}-offset-md-${this.offset}` : '';
      return classe;
    }
  }
}
</script>
