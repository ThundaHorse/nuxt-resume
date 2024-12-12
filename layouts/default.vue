<template>
  <v-app dark>
    <!-- Content -->
    <v-main id="main">
      <!-- <v-container pa-0> -->
      <v-main fill-height>
        <nuxt />
      </v-main>
    </v-main>

    <!-- Footer -->
    <Footer />
  </v-app>
</template>

<script>
  import Footer from '../components/layout-components/Footer.vue';

  export default {
    name: 'default',
    components: {
      Footer
    },
    data() {
      return {};
    },
    methods: {}
  };
</script>

<style></style>
