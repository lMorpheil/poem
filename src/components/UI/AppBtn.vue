<script setup>

</script>

<template>
  <button class="btn" type="button"></button>
</template>

<style scoped lang="scss">
.btn {
  display: block;
  width: 2rem;
  height: 2rem;
  border: 2px solid black;
  cursor: pointer;
  padding: 0;
  background-color: #fff;

  &.active {
    background-color: black;
  }
}
</style>
