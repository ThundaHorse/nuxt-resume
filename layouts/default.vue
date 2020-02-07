<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :href="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title v-text="title" />
      <v-spacer />
    </v-app-bar>
    <v-content>
      <!-- <v-container pa-0> -->
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer :fixed="fixed" app>
      <span><VuetifyLogo style="height: 25px; width: 25px;"/></span>
    </v-footer>
  </v-app>
</template>

<script>
  import VuetifyLogo from '../components/VuetifyLogo';

  export default {
    components: {
      VuetifyLogo
    },
    data() {
      return {
        clipped: false,
        drawer: false,
        fixed: false,
        items: [
          {
            icon: '',
            title: '',
            to: ''
          },
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
    }
  };
</script>
