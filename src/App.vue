<script setup>
import Navbar from "./share/Navbar.vue"
</script>

<!--template>

  <div class="Top">

    <Navbar />



    <RouterView />

    

  </div>
</template-->


<template>
  <div class="app">
    <div class="navbar">
      <navbar></navbar>
        <router-view v-slot="{ Component }">
          <transition name="page-opacity" mode="out-in">
            <component :is="Component"></component>
          </transition>
        </router-view>
    </div>
  </div>
</template>



<style>

.app {
  position: relative;
  z-index: 0;
  min-width: fit-content;
  min-height: 100vh;
  background-size: cover;
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-blend-mode: overlay;
}

.app::after {
  content: "";
  position: absolute;
  z-index: 1;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  opacity: 0.9;
  background-size: cover;
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-blend-mode: overlay;
  animation: background-flicker 7s linear infinite;
}


.page-opacity-enter-from{
  opacity: 0;
  transform: translateY(-100px);
}

.page-opacity-enter-active{
  transition: all 0.3s ease-out;
}

.page-opacity-leave-to{
  opacity: 0;
  transform: translateY(100px);
}

.page-opacity-leave-active{
  transition: all 0.3s ease-in;
}

@keyframes background-flicker {
  0% {
    opacity: 0.9;
  }
  2% {
    opacity: 0.05;
  }
  3% {
    opacity: 0.05;
  }
  4% {
    opacity: 0.9;
  }
  41% {
    opacity: 0.7;
  }
  42% {
    opacity: 0.05;
  }
  44% {
    opacity: 0.05;
  }
  45% {
    opacity: 0.7;
  }
  65% {
    opacity: 0.5;
  }
  70% {
    opacity: 0.4;
  }
  72% {
    opacity: 0.1;
  }
  73% {
    opacity: 0.1;
  }
  74% {
    opacity: 0.3;
  }
  100% {
    opacity: 0.9;
  }
}

.navbar {
  position: relative;
  z-index: 2;
}



</style>




<style scoped>/*
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
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

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}*/
</style>
