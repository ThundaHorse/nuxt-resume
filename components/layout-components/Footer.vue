<template>
  <div class="main-foot">
    <v-footer :fixed="true" app>
      <span><VuetifyLogo style="height: 25px; width: 25px;"/></span>
    </v-footer>
  </div>
</template>

<script>
import VuetifyLogo from '../VuetifyLogo.vue';

export default {
  components: {
    VuetifyLogo
  },
  data: function() {
    return {};
  }
};
</script>