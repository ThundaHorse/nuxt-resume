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
    return {
      items: [
        {
          icon: 'mdi-home',
          to: '/',
          name: 'Home'
        },
        {
          icon: 'mdi-information-outline',
          to: '/about',
          name: 'About'
        },
        {
          icon: 'mdi-toolbox-outline',
          to: '/projects',
          name: 'Projects'
        },
        {
          icon: 'mdi-home',
          to: '/home',
          name: 'Home'
        }
      ],
      socialLinks: [
        {
          icon: 'mdi-apps',
          title: 'Github',
          to: 'https://www.github.com/ThundaHorse'
        },
        {
          icon: 'mdi-apps',
          title: 'LinkedIn',
          to: 'https://www.linkedin.com/in/abrahamtkim/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Medium',
          to: 'https://medium.com/@abekeeem'
        }
      ],
      miniVariant: false,
      title: 'AK'
    };
  },
  methods: {}
};
</script>

<style></style>
