

<script setup lang="ts">
  import { ref } from 'vue';

  // defineProps<{
  //   title: string;
  // }>()

  defineProps(['title'])
  
  defineEmits(['enlarge-text', 'decrease-text'])

  // const emit = defineEmits<{
  //   (e: 'enlarge-text'', id: number): void
  //   (e: 'decrease-text', value: string): void
  // }>()

  // defineEmits<{
  //   enlargeText: [id: number]
  //   decreaseText: [value: string]
  // }>()

  const posts = ref([
    { id: 1, title: 'My journey with Vue' },
    { id: 2, title: 'Blogging with Vue' },
    { id: 3, title: 'Why Vue is so fun' },
    { id: 4, title: 'Why Vue is so fun 2' }
  ])
</script>

<template>
  <div class="listViewItem">
    <ul>
      <li v-for="post in posts" :key="post.id">{{ post.title }}</li>
    </ul>
    <slot></slot>
    <button @click="$emit('enlarge-text')">Enlarge text</button>
    <button @click="$emit('decrease-text')">Enlarge text</button>
  </div>
</template>

<style scoped>
@media (min-width: 1024px) {}
</style>
