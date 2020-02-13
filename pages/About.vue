<template>
  <div class="about">
    <About />
    <Skills />
  </div>
</template>

<style>
</style>

<script>
  import About from '~/components/page-components/About.vue'
  import Skills from '~/components/page-components/Skills.vue'

  export default {
    components: {
      About,
      Skills
    },
    data: function () {
      return {}
    },
    created: function () { },
    methods: {}
  }
</script>
