<script setup>
const { stanza } = defineProps({
  stanza: Object,
})
</script>

<template>
  <p class="stanza" v-if="stanza.visible">
    <template v-for="line in stanza.lines">
      <span>{{ line }}</span><br>
    </template>
  </p>
</template>

<style scoped lang="scss">
.stanza {

  &:not(:first-child) {
    margin-top: 1.5rem;
  }

  > span {

    &:nth-of-type(even) {
      margin-left: 4rem;
    }
  }
}
</style>
