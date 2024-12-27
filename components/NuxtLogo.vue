<template>
  <img class="nuxt-logo" src="../static/nuxt-logo.png" alt="Nuxt Logo" />
</template>

<script>
  export default {
    data() {
      return {};
    }
  };
</script>

<style>
  .nuxt-logo {
    width: 180px;
    transform: rotateY(560deg);
    animation: turn 5s ease-out forwards 1s;
  }

  @keyframes turn {
    100% {
      transform: rotateY(0deg);
    }
  }
</style>
