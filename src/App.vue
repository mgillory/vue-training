<template>
  <div id="app">
    <nav>
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
    </nav>
    <transition name="router-animation">
      <router-view />
    </transition>
  </div>
</template>

<script>
import Skills from './components/Skills.vue'

export default {
  name: 'app',
  components: {
    Skills
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css?family=Montserrat:400,700');
  body {
    background-color: #EEEEEE;
    font-family: 'Montserrat', sans-serif;
    display: grid;
    grid-template-rows: auto;
    justify-items: center;
    padding-top: 50px;
  }
  body, html {
    margin: 0;
    height: 100%;
  }
  #app {
      width: 50%;
  }
  nav {
    padding: 20px 20px 20px 0;
  }
  nav a {
    padding: 10px;
    text-decoration: none;
    background: #fff;
    border-radius: 3px;
    color: rgb(0, 110, 255);
    font-weight: bold;
    margin-right: 15px;
  }
  .page {
    position: fixed;
    width: inherit;
  }
  .router-animation-enter-active {
    animation: coming 1s;
    animation-delay: .5s;
    opacity: 0;
  }
  .router-animation-leave-active {
    animation: going 1s;
  }
  @keyframes going {
    from {
      transform: translateX(0);

    }
    to {
      transform: translateX(-50px);
      opacity: 0;
    }
  }
  
  @keyframes coming {
    from {
      transform: translateX(-50px);

    }
    to {
      transform: translateX(0);
      opacity: 1;
    }
  }
</style>
