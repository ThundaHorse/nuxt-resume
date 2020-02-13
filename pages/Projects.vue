<template>
  <div class="projects">
    <h1>Here are some projects that I have worked on:</h1>
    <Projects />

    <h1>My skills include:</h1>
    <Skills />
  </div>
</template>

<style>
.projects {
  width: 100%;
}
</style>

<script>
import Projects from '~/components/page-components/Projects.vue';
import Skills from '~/components/page-components/Skills.vue';

export default {
  components: {
    Projects,
    Skills
  },
  data: function() {
    return {};
  },
  created: function() {},
  methods: {}
};
</script>