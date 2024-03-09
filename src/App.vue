<template>
  <div class="row">
    <AppPoem
        :title="title"
        :author="author"
        :poem="poem"
    />
  </div>
</template>

<script setup>
import { ref } from "vue";
import AppPoem from "@/components/AppPoem.vue";

const title = ref('Invictus');
const author = ref('By William Ernest Henley');
const poem = ref([
  {
    id: 1,
    visible: true,
    lines: [
      'Out of the night that covers me,',
      'Black as the pit from pole to pole,',
      'I thank whatever gods may be',
      'For my unconquerable soul.',
    ],
  },
  {
    id: 2,
    visible: true,
    lines: [
      'In the fell clutch of circumstance',
      'I have not winced nor cried aloud.',
      'Under the bludgeonings of chance',
      'My head is bloody, but unbowed.',
    ],
  },
  {
    id: 3,
    visible: true,
    lines: [
      'Beyond this place of wrath and tears',
      'Looms but the Horror of the shade,',
      'And yet the menace of the years',
      'Finds and shall find me unafraid.',
    ],
  },
  {
    id: 4,
    visible: true,
    lines: [
      'It matters not how strait the gate,',
      'How charged with punishments the scroll,',
      'I am the master of my fate,',
      'I am the captain of my soul.',
    ],
  },
]);
</script>

<style lang="scss">
html {
  // Считает рамер шрифта в зависимости от ширины экрана,
  // !important нужен чтобы перебить слити css-reset,
  font-size: calc(7px + (64 - 7) * (100vw - 450px) / (8000 - 450)) !important;
}

.row {
  margin-right: auto;
  margin-left: auto;
  max-width: 66rem;
  padding-right: 2rem;
  padding-left: 2rem;
}
</style>
