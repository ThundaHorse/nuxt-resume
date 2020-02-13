<template>
  <div class="about-me">
    <v-card class="mx-auto" max-width="600" shaped="true">
      <div
        v-anime="{
          translateX: [{ value: [-100, 0], duration: 1000, delay: 200 }],
          opacity: [{ value: [0, 1], duration: 1000, delay: 200 }],
          easing: 'easeOutSine(1, .5)',
          loop: false
        }"
        class="text-center"
      >
        <img
          src="../../static/bigbear copy.png"
          alt="intro-pic"
          style="height: 250px; width: 250px; border-radius: 50%;"
        />
      </div>
      <v-spacer />
      <v-container fluid>
        <v-row dense>
          <v-card-text>
            <div
              v-anime="{
                translateX: [
                  { value: [-100, -10], duration: 1000, delay: 200 }
                ],
                opacity: [{ value: [0, 1], duration: 1000, delay: 200 }],
                easing: 'easeOutSine(1, .5)',
                loop: false
              }"
            >
              <h1 class="display-1 text-center font-weight-regular">
                About me
              </h1>
            </div>
            <div
              v-anime="{
                translateX: [{ value: [100, -10], duration: 1000, delay: 200 }],
                opacity: [{ value: [0, 0.8], duration: 1000, delay: 200 }],
                easing: 'easeOutSine(1, .5)',
                loop: false
              }"
            >
              <h4 class="text-center font-weight-regular">
                I'm a software engineer currently residing in Sunrise, FL
                originally from Atlanta, GA. I graduated from Georgia State
                University with a degree in Political Science which helped me
                understand how to manipulate data at a fundamental level. During
                my undergraduated studies I started working for Apple and after
                graduating, I became a Senior Advisor for AppleCare, with Apple
                I learned how to always be open to new information as well as
                never settling with what I know, because there is always new
                information to learn! I was always intruigued by software
                development and taught myself Javascript and Ruby throughout my
                undergraduate studies. In 2019 I decided to attend Actualize
                Coding Bootcamp in Chicago, IL to pursue my passion.
              </h4>
            </div>
          </v-card-text>
        </v-row>
      </v-container>
      <v-card-actions>
        <v-btn text color="deep-purple accent-4">
          Learn More
        </v-btn>
      </v-card-actions>
    </v-card>
  </div>
</template>

<script>
import Skills from './Skills.vue';

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
