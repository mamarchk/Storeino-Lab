<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <nav>
    <div class="container">
      <div class="wrapper">
        <h1>logo</h1>
        <ul class="links">
          <li>
            <RouterLink to="/">Home</RouterLink>
          </li>
          <li>
            <RouterLink to="/about">About</RouterLink>
          </li>
          <li>
            <RouterLink to="/program">Program</RouterLink>
          </li>
          <button>
            <RouterLink to="/register">Register</RouterLink>
          </button>
        </ul>
        <button>button</button>
      </div>
    </div>
  </nav>

  <RouterView />
</template>

<style scoped>
nav {
  width: 100%;
  background-color: white;
  padding: 20px;
}
/* 

.wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.links {
  display: flex;
  justify-content: space-between;
  align-items: center;
} 
*/

@media (min-width: 720px) {}

@media (min-width: 1020px) {}

</style>
