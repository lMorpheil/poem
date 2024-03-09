<script setup>
import AppHead from "@/components/AppHead.vue";
import AppPoemBody from "@/components/AppPoemBody.vue";

const { title, author, poem } = defineProps({
  title: String,
  author: String,
  poem: {
    type: Array,
    required: true,
  }
})
</script>

<template>
  <AppHead
      :title="title"
      :author="author"
  />
  <AppPoemBody :poem="poem" />
</template>
