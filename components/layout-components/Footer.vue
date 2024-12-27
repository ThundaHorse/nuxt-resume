<template>
  <div class="main-foot">
    <v-footer :fixed="true" app>
      <span>
        <VueLogo style="height: 25px; width: 25px;" />
        <NuxtLogo style="height: 25px; width: 25px;" />
        <VuetifyLogo style="height: 25px; width: 25px;" />
      </span>
    </v-footer>
  </div>
</template>

<script>
  import VuetifyLogo from '../VuetifyLogo.vue';
  import VueLogo from '../VueLogo.vue';
  import NuxtLogo from '../NuxtLogo.vue';

  export default {
    components: {
      VuetifyLogo,
      VueLogo,
      NuxtLogo
    },
    data: function() {
      return {};
    }
  };
</script>

<style>
  .v-footer {
    background-color: black !important;
  }
</style>
