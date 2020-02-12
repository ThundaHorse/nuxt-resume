<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <!-- Page Sections -->
      <v-list v-for="(item, idx) in items" :key="idx">
        <v-list-item>
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <nuxt-link :to="item.to">
              <v-list-item-title v-text="item.name" />
            </nuxt-link>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title v-text="title" />
      <v-spacer />
    </v-app-bar>

    <!-- Content -->
    <v-content>
      <!-- <v-container pa-0> -->
      <v-container>
        <nuxt />
      </v-container>
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
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          to: '/',
          name: 'Home'
        },
        {
          icon: 'mdi-apps',
          to: '/about',
          name: 'About'
        },
        {
          icon: 'mdi-apps',
          to: '/projects',
          name: 'Projects'
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
      right: true,
      rightDrawer: false,
      title: 'ABRAHAM KIM'
    };
  },
  methods: {}
};
</script>
