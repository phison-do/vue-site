

<script lang="ts" setup>
  import ListViewTsVue from '@/components/ListViewTs.vue';
  import { ref } from 'vue';

  const postFontSize = ref(1)
</script>

<template>
  <div class="about">
    <div :style="{ fontSize: postFontSize + 'em' }">
      <ListViewTsVue title="Mijn Lijst" @enlarge-text="postFontSize += 0.1" @decrease-text="postFontSize += -0.1">
        test slot
      </ListViewTsVue>
    </div>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
