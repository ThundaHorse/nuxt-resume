<template>
  <div class="about">
    <v-container>
      <v-layout row wrap align-center justify-center>
        <v-row justify="space-around">
          <v-col cols="auto" class="ml-auto" />
          <v-col cols="auto">
            <About />
          </v-col>
          <v-col cols="auto" class="mr-auto"></v-col>
        </v-row>
      </v-layout>
    </v-container>
  </div>
</template>

<style>
  .about {
    width: 100%;
  }
</style>

<script>
  import About from '~/components/page-components/About.vue';
  import Skills from '~/components/page-components/Skills.vue';
  export default {
    components: {
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
