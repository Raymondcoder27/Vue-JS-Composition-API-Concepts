<template>
  <div>
    <h3>This is the about page</h3>
    <input type="text" v-autofocus>
    <ul>
      <li 
      v-for="post in posts" 
      :key="post.id">
        <RouterLink :to="`/postDetail/${ post.id }`">{{ post.title }}</RouterLink>
      </li>
      <!-- <li>
        <RouterLink to="/postDetail/id2">Post 2</RouterLink>
      </li>
      <li>
        <RouterLink to="/postDetail/id3">Post 3</RouterLink>
      </li> -->
    </ul>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import {vAutofocus} from '@/directives/vAutofocus'

//posts
const posts = ref([
  {
    id: 'id1',
    title: 'Post 1'
  },
  {
    id: 'id2',
    title: 'Post 2'
  },
  {
    id: 'id3',
    title: 'Post 3'
  },
  {
    id: 'id4',
    title: 'Post 4'
  },
])

</script>

<!-- <template>
  <div>
    <h3>Hello</h3>
  </div>
</template>

<script setup>
</script> -->

