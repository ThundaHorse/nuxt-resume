<template>
  <div class="about">
    <Intro />
    <About />
    <Skills />
  </div>
</template>

<style>
</style>

<script>
import Intro from '~/components/page-components/Intro.vue';
import About from '~/components/page-components/About.vue';
import Skills from '~/components/page-components/Skills.vue';

export default {
  components: {
    Intro,
    About,
    Skills
  },
  data: function() {
    return {};
  },
  created: function() {},
  methods: {}
};
</script>