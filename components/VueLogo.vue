<template>
  <img class="vue-logo" src="../static/vue-logo.png" alt="Vue Logo" />
</template>

<script>
  export default {
    data() {
      return {};
    }
  };
</script>

<style>
  .vue-logo {
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
