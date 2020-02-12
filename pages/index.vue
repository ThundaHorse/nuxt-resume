<template>
  <v-layout column justify-center align-center>
    <v-row id="intro" align="center" justify="center">
      <v-col class="text-center" cols="12">
        <h1 class="display-1 font-weight-regular mb-4">Hi there!</h1>
        <h4 class="subheading font-weight-regular">
          My name is Abraham Kim. I put pieces of the web together. I'm a
          software engineer who crafts precise and aesthetically pleasing web
          apps. Exploring new languages and frameworks is what I enjoy among
          many other things. I like to focus on making sure my work is
          thouroughly tested and fit to be scaled and maintained. Honing my
          skills to create efficient and concise code is my goal.
        </h4>
      </v-col>
    </v-row>
    <About />
  </v-layout>
</template>

<script>
import Logo from '~/components/Logo.vue';
import VuetifyLogo from '~/components/VuetifyLogo.vue';
import anime from 'animejs/lib/anime.es.js';
import About from '~/components/About.vue';
import Projects from '~/components/Projects.vue';

export default {
  components: {
    About,
    Projects
  },
  data: function() {
    return {};
  }
};
</script>
