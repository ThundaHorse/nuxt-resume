<template>
  <v-container fluid>
    <v-row align="center" justify="center">
      <v-col class="text-center" cols="auto">
        <v-card id="intro" class="mx-auto" max-width="550" :raised="true">
          <img
            v-anime="{
              targets: '.property-keyframes-demo .el',
              translateX: [{ value: [-100, 0], duration: 1000, delay: 200 }],
              opacity: [{ value: [0, 1], duration: 1000, delay: 200 }],
              easing: 'easeOutSine(1, .5)',
              loop: false
            }"
            src="../static/headshot-min.png"
            alt="headshot"
            style="height: 190px; width: 170px; border-radius: 50%; position: relative; top: -40px; border: solid 2px white;"
          />
          <v-card-subtitle class="pb-0">
            <div
              v-anime="{
                targets: '.property-keyframes-demo .el',
                translateX: [{ value: [-100, 0], duration: 1000, delay: 200 }],
                opacity: [{ value: [0, 1], duration: 1000, delay: 200 }],
                easing: 'easeOutSine(1, .5)',
                loop: false
              }"
            >
              <h1 class="display-1 font-weight-regular mb-4">Hello there!</h1>
            </div>
          </v-card-subtitle>
          <v-card-text class="text--primary">
            <div
              class="wrapper"
              v-anime="{
                opacity: [{ value: [0, 1], duration: 1000, delay: 200 }],
                easing: 'easeInOutExpo'
              }"
            >
              <h2 class="subheading font-weight-light">
                My name is Abraham Kim. I'm a full stack developer who crafts
                precise and aesthetically pleasing web apps. Exploring new
                languages and frameworks is what I enjoy among many other
                things. I like to focus on making sure my work is thouroughly
                tested and fit to be scaled and maintained. Honing my skills to
                create efficient and concise code is my goal.
              </h2>
            </div>
          </v-card-text>
          <v-spacer></v-spacer>
          <v-card-actions>
            <v-row>
              <v-col>
                <v-btn color="orange accent-2" text href="https://www.github.com/ThundaHorse">Github</v-btn>
                <v-btn
                  color="light-blue darken-1"
                  text
                  href="https://www.linkedin.com/in/abrahamtkim/"
                >LinkedIn</v-btn>
                <v-btn color="light-green accent-3" text href="https://medium.com/@abekeeem">Medium</v-btn>
              </v-col>
            </v-row>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<style>
  #intro {
    box-shadow: rgba(0, 0, 0, 0.16) 0px 3px 6px;
    background-color: rgba(126, 125, 125, 0.16);
    border-radius: 25px;
    margin-top: 15px;
  }
</style>

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
