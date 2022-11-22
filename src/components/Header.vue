<script setup>
import { ref, onMounted } from "vue";

const mobile = ref(null);
const mobileNav = ref(null);
const windowWidth = ref(null);

const toggleMobileNav = () => {
  mobileNav.value = !mobileNav.value;
};

const closeMobileNav = () => {
  mobileNav.value = false;
};

const checkScreen = () => {
  windowWidth.value = window.innerWidth;
  if (windowWidth.value <= 1000) {
    mobile.value = true;
    return;
  }
  mobile.value = false;
  mobileNav.value = false;
};

onMounted(() => {
  checkScreen();
  window.addEventListener("resize", checkScreen);
});
</script>

<template>
  <header>
    <div class="container">
      <nav>
        <div class="branding">
          <a href="#"
            ><img src="../assets/img/logo-StoreinoLab.png" alt="logo"
          /></a>
        </div>
        <ul v-show="!mobile" class="navigation">
          <li>
            <a class="link" href="#a-propos">A PROPOS</a>
          </li>
          <li>
            <a class="link" href="#thematiques">THEMATIQUES</a>
          </li>
          <li>
            <a class="link" href="#programme">PROGRAMME</a>
          </li>
          <li>
            <a class="link btn" href="#inscrivez-vous">INSCRIVEZ-VOUS</a>
          </li>
        </ul>
        <div class="icon">
          <i
            @click="toggleMobileNav"
            v-show="mobile"
            class="fa fa-bars"
            :class="{ 'icon-active': mobileNav }"
          ></i>
        </div>
        <transition name="mobile-nav">
          <ul v-show="mobileNav" class="dropdown">
            <li @click="closeMobileNav">
              <a class="link" href="#a-propos">A PROPOS</a>
            </li>
            <li @click="closeMobileNav">
              <a class="link" href="#thematiques">THEMATIQUES</a>
            </li>
            <li @click="closeMobileNav">
              <a class="link" href="#programme">PROGRAMME</a>
            </li>
            <li @click="closeMobileNav">
              <a class="link" href="#inscrivez-vous">INSCRIVEZ-VOUS</a>
            </li>
          </ul>
        </transition>
      </nav>
    </div>
  </header>
</template>

<style scoped>
.container {
  position: relative;
}

header {
  margin-top: 15px;
  z-index: 999;
  width: 100%;
  transition: 0.5s ease all;
  /* position: fixed; */
}

header .container {
  background-color: rgba(255, 255, 255, 0.75);
  border-radius: 25px;
}

header nav {
  position: relative;
  display: flex;
  flex-direction: row;
  padding: 2px 0;
  width: 90%;
  margin: 0 auto;
  transition: 0.5s ease all;
}

header nav ul,
header nav .link {
  font-weight: 500;
  color: var(--blueColor);
  list-style: none;
  text-decoration: none;
}

header nav ul li {
  text-transform: uppercase;
  padding: 16px;
  margin-left: 16px;
}

header nav .link {
  font-size: 14px;
  padding-bottom: 4px;
  border-bottom: 2px solid transparent;
  transition: 0.5s ease all;
}

header nav .link:hover {
  color: var(--cyanColor);
  border-color: var(--cyanColor);
}

header nav .link.btn {
  border: none;
  color: #f5f5f5;
  background-color: var(--cyanColor);
  padding: 10px;
  border-radius: 25px;
}

header nav .link.btn:hover {
  color: #f5f5f5;
  background-color: var(--blueColor);
}

header nav .branding {
  display: flex;
  align-items: center;
}

header nav .branding img {
  width: 80px;
  cursor: pointer;
  transition: 0.5s ease all;
}

.navigation {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  flex: 1;
}

.icon {
  display: flex;
  align-items: center;
  position: absolute;
  top: 0;
  right: 24px;
  height: 100%;
}

.icon i {
  cursor: pointer;
  font-size: 24px;
  color: var(--blueColor);
  transition: 0.8s ease all;
}

.icon-active {
  transform: rotate(180deg);
}

.dropdown {
  margin-top: 0;
  display: flex;
  flex-direction: column;
  position: fixed;
  width: 100%;
  max-width: 200px;
  height: 100%;
  background: gray;
  z-index: 999;
  top: 0;
  left: 0;
}

.dropdown li {
  margin-left: 0;
}

.dropdown li .link {
  color: #f5f5f5;
}

.mobile-nav-enter-active,
.mobile-nav-leave-active {
  transition: 1s ease all;
}

.mobile-nav-enter-from,
.mobile-nav-leave-to {
  transform: translateX(-350px);
}

.mobile-nav-enter-to {
  transform: translateX(0);
}

@media (min-width: 1140px) {
  header nav {
    max-width: 1140px;
  }
}
</style>
