<template>
  <v-layout column justify-center align-center>
    <Intro />
    <About />
    <Projects />
  </v-layout>
</template>

<script>
import Logo from '~/components/Logo.vue';
import VuetifyLogo from '~/components/VuetifyLogo.vue';
import anime from 'animejs/lib/anime.es.js';
import Intro from '~/components/Intro.vue';
import About from '~/components/About.vue';
import Projects from '~/components/Projects.vue';

export default {
  name: 'index',
  components: {
    Intro,
    About,
    Projects
  },
  props: {
    selected: String
  },
  data: function() {
    return {};
  }
};
</script>
