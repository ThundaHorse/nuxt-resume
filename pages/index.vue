<template>
  <v-container fluid>
    <v-row align="center" justify="center">
      <v-col class="text-center" cols="12">
        <div
          v-anime="{
            targets: '.property-keyframes-demo .el',
            translateX: [{ value: [-100, 0], duration: 1000, delay: 200 }],
            opacity: [{ value: [0, 1], duration: 1000, delay: 200 }],
            easing: 'easeOutSine(1, .5)',
            loop: false
          }"
        >
          <img
            src="../static/headshot-min.png"
            alt="headshot"
            style="height: 190px; width: 170px; border-radius: 50%; opacity: 0.8;"
          />
          <h1 class="display-1 font-weight-regular mb-4">Hello there!</h1>
        </div>
        <div
          v-anime="{
            targets: '.linear-easing-demo .el',
            translateX: [100, 0],
            direction: 'normal',
            loop: false,
            opacity: [{ value: [0, 1], duration: 1000, delay: 200 }],
            easing: 'linear'
          }"
        >
          <h4 class="subheading font-weight-light">
            My name is Abraham Kim. I put pieces of the web together. I'm a
            software engineer who crafts precise and aesthetically pleasing web
            apps. Exploring new languages and frameworks is what I enjoy among
            many other things. I like to focus on making sure my work is
            thouroughly tested and fit to be scaled and maintained. Honing my
            skills to create efficient and concise code is my goal.
          </h4>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import Logo from '~/components/Logo.vue';
import VuetifyLogo from '~/components/VuetifyLogo.vue';

export default {
  name: 'index',
  components: {},
  data: function() {
    return {};
  }
};
</script>
