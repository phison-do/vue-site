<template>
  <div class="listViewItem">
    {{ title }}
    <ul>
      <li v-for="post in posts" :key="post.id">{{ post.title }}</li>
    </ul>
    <div><slot></slot></div>
    <button @click="$emit('enlarge-text')">Enlarge text</button>
    <button @click="$emit('decrease-text')">Enlarge text</button>
  </div>
</template>

<script lang="ts">
  import { defineComponent } from "vue";
  import { ref } from 'vue';

  const posts = ref([
    { id: 1, title: 'My journey with Vue' },
    { id: 2, title: 'Blogging with Vue' },
    { id: 3, title: 'Why Vue is so fun' },
    { id: 4, title: 'Why Vue is so fun 2' }
  ])

  export default defineComponent({
    emits: ['enlarge-text', 'decrease-text'],
    props: {
      title: String,
    },
    data() {
      return {
        posts
      }
    }
  });
</script>  

<style scoped>
@media (min-width: 1024px) {}
</style>
