<template>
  <!-- <header> -->
    <div>
      <div class="user-data">
      <!-- {{ userData.name }}  @{{ userData.username }} -->
    </div>
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/post">Post</RouterLink>
        <RouterLink to="/modal">Modal</RouterLink>
        <!-- <RouterLink to="/post-detail">About</RouterLink> -->
      </nav>
  <!-- </header> -->

  <RouterView />
    </div>
</template>

<script setup>
// import { RouterLink, RouterView } from 'vue-router'
// import HelloWorld from './components/HelloWorld.vue'
import {reactive, provide} from 'vue'

const userData = reactive({
  name: 'Raymond', 
  username: 'mwebe@raymond'
})

provide('userData', userData)

</script>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

.user-data{
  position:absolute;
  background: beige;
  top: 0;
  right: 0;
  font-size: 12px;
  padding: 5px;
}

</style>
