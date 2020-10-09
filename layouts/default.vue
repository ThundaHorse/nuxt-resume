<template>
  <v-app dark>
    <!-- Content -->
    <v-content id="main">
      <!-- <v-container pa-0> -->
      <v-content fill-height>
        <nuxt />
      </v-content>
    </v-content>

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
