<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'my-button'
}
</script>

<style scoped>
.btn {
  padding: 10px 15px;
  background: none;
  color: darkgreen;
  border: 1px solid darkgreen;
}
</style>