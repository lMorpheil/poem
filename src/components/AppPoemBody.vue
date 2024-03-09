<script setup>
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
      <button
          v-for="item in poem"
          :class="['btn', {active: item.visible}]"
          type="button"
          :key="item.id"
          @click="handleClick(item.id)"
      ></button>
    </div>
    <div class="poem">
      <template v-for="stanza in poem" :key="stanza.id">
        <p class="stanza" v-if="stanza.visible">
          <template v-for="line in stanza.lines">
            <span>{{ line }}</span><br>
          </template>
        </p>
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

.poem {
  font-size: 2.5rem;
}

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
