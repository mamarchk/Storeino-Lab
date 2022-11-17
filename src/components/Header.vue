<script setup>
import { RouterLink, RouterView } from "vue-router";
import { ref } from "vue";

const links = ref(false);
const toggleLinks = () => {
  links.value = !links.value;
};
</script>

<template>
  <header>
    <div class="container">
      <a href="#">
        <img class="logo" src="../assets/img/logo StoreinoLab.png" alt="logo" />
      </a>
      <div class="links">
        <span @click="toggleLinks" class="icon">
          <i class="fa-solid fa-bars-staggered"></i>
        </span>
        <ul v-show="links">
          <li>
            <a href="#home">Home</a>
          </li>
          <li>
            <a href="#about">About</a>
          </li>
          <li>
            <a href="#program">Program</a>
          </li>
          <li>
            <a href="#register">Register</a>
          </li>
        </ul>
      </div>
    </div>
  </header>
</template>

<style scoped>
header {
  padding: 20px;
}
header .container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
header .logo {
  width: 200px;
}
header .links {
  position: relative;
}
header .links .icon i {
  font-size: 30px;
  cursor: pointer;
  color: #333;
  transition: all 0.3s ease;
}
header .links .icon i:hover {
  color: #568ffc;
}
header .links ul {
  list-style: none;
  margin: 0;
  padding: 0;
  background: #f6f6f6;
  position: absolute;
  right: 0;
  min-width: 200px;
  top: calc(100% + 15px);
}
header .links ul::before {
  content: "";
  position: absolute;
  border-width: 10px;
  border-style: solid;
  border-color: transparent transparent #f6f6f6 transparent;
  right: 5px;
  top: -20px;
}
/* header .links:hover ul {
  display: block;
} */
header .links ul li a {
  display: block;
  padding: 15px;
  text-decoration: none;
  color: #333;
  transition: all 0.3s ease;
}
header .links ul li a:hover {
  padding-left: 25px;
}
header .links ul li:not(:last-child) a {
  border-bottom: 1px solid #ddd;
}
</style>
