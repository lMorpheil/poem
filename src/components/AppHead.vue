<script setup>
const { title, author } = defineProps({
  title: String,
  author: String,
})
</script>

<template>
  <div class="head">
    <h1 class="title">
      {{ title }}
    </h1>
    <div class="author">
      {{ author }}
    </div>
  </div>
</template>

<style scoped lang="scss">
.head {
  display: flex;
  align-items: baseline;
  justify-content: flex-end;
}

.title {
  font-size: 4rem;
}

.author {
  font-size: 2rem;
  margin-left: 6rem;
}
</style>
