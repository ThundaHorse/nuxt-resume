<template>
  <div class="about">
    <v-row id="about-me" align="center" justify="center">
      <v-col class="text-center" cols="12">
        <h1 class="display-1 font-weight-regular mb-4">About me</h1>
        <h4 class="subheading font-weight-regular">
          I'm a software engineer currently residing in Sunrise, FL originally
          from Atlanta, GA. I graduated from Georgia State University with a
          degree in Political Science. During my undergraduated studies I
          started working for Apple and after graduating, I became a Senior
          Advisor for AppleCare. I studied software development on my own
          throughout highschool and my undergraduate studies, come 2019 I
          decided to attend Actualize Coding Bootcamp in Chicago, IL to pursue
          my passion. During my time at Actualize, I became familiar with the
          following technologies:
        </h4>
      </v-col>
    </v-row>
    <Skills />
  </div>
</template>

<script>
import Skills from '~/components/Skills.vue';

export default {
  components: {
    Skills
  },
  data: function() {
    return {};
  },
  created: function() {},
  methods: {}
};
</script>