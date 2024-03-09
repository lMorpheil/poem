<script setup>
import AppBtn from "@/components/UI/AppBtn.vue";
import AppStanza from "@/components/AppStanza.vue";

const handleClick = (id) => {
  const visibleEl = poem.filter((el) => el.visible);

  poem.forEach((el) => {
    if (el.id === id && (visibleEl.length > 1 || el.visible !== true)) {
      el.visible = !el.visible
    }
  })
}
const { poem } = defineProps({
  poem: {
    type: Array,
    required: true,
  }
})
</script>

<template>
  <div class="text">

    <div class="btn-block">
      <AppBtn v-for="item in poem"
              :class="{active: item.visible}"
              type="button"
              :key="item.id"
              @click="handleClick(item.id)"
      />
    </div>

    <div class="poem">
      <template v-for="stanza in poem" :key="stanza.id">
        <AppStanza :stanza="stanza" />
      </template>
    </div>

  </div>
</template>

<style scoped lang="scss">
.text {
  display: flex;
  align-items: flex-start;
  margin-top: 1rem;
}

.btn-block {
  display: flex;
  align-items: center;
  justify-content: flex-end;
  margin-top: 0.3rem;
  margin-right: 2rem;

  > * {
    margin-right: 0.6rem;
    margin-left: 0.6rem;
  }
}

.poem {
  font-size: 2.5rem;
}
</style>
