<template>
  <div
    class="projects"
    v-anime="{
        translateX: [{ value: [100, 0], duration: 1000, delay: 200 }],
        opacity: [{ value: [0, 1], duration: 1000, delay: 200 }],
        easing: 'easeOutSine(1, .5)',
        loop: false
      }"
  >
    <v-container>
      <v-row align="center">
        <v-item-group v-model="window" class="shrink mr-6" mandatory tag="v-flex">
          <v-item v-for="(project, idx) in projects" :key="idx" v-slot:default="{ active, toggle }">
            <div>
              <v-btn :input-value="active" icon @click="toggle">
                <v-icon>mdi-record</v-icon>
              </v-btn>
            </div>
          </v-item>
        </v-item-group>
        <v-col>
          <v-window v-model="window" vertical>
            <v-window-item v-for="(project, idx) in projects" :key="idx">
              <v-card flat :ripple="true" :light="idx % 2 !== 0" class="pa-2">
                <v-card-text>
                  <v-row class="mb-4" align="center">
                    <!-- <v-avatar color="grey" class="mr-4"></v-avatar> -->
                    <v-avatar class="mr-4">
                      <img :src="project.img" :alt="project.name" />
                    </v-avatar>
                    <strong class="title">{{ project.name }}</strong>
                    <v-spacer></v-spacer>
                    <v-btn icon :href="project.url">
                      <v-icon>mdi-rice</v-icon>
                    </v-btn>
                  </v-row>
                  <p>{{ project.desc }}</p>
                </v-card-text>
              </v-card>
            </v-window-item>
          </v-window>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
  export default {
    data: function() {
      return {
        projects: [
          {
            name: 'Our Daily Memes',
            desc:
              'Users can sign up for accounts or browser without an account. Users can post memes and a short description of their meme. Images are stored in AWS. The back-end is built with Ruby on Rails and a Vue.JS Front-end. Each post has individual likes/dislikes and comments. Users can comment on a post and see their comments in real-time.',
            url: 'https://ourdailymemes.netlify.com/',
            img: require('../../static/memes-min.png')
          },
          {
            name: 'Mock E-Commerce App',
            desc:
              'Users are required to sign in to view their postings. Items can have multiple attached images, made possible with AWS. Each item page features a chat box for inquiries. Currently still under construction for addition of dummy payment features.',
            url: 'https://compassionate-wilson-a34cfc.netlify.com/',
            img: require('../../static/dollar-min.png')
          },
          {
            name: "Let's go to Disney",
            desc:
              'An app designed to help users create and keep tabs on a trip for Disney. In addition to creating an itinerary to plan a day at Disney, attraction wait times are updated in real-time by utilizing Action Cable and custom rake tasks in Rails that utilizes a custom script to be run at set intervals. in conjunction with the API to gather times, the script file access the Rails database and updates the attraction models which in turn is updated in the Vue app by Action Cable.',
            url: 'https://github.com/ThundaHorse/disney_vue_app',
            img: require('../../static/cloudCaste-min.jpg')
          },
          {
            name: 'Vuex Memory Game',
            desc:
              'A user can choose two cards and if they match, they stay unflipped and your score goes up! Vuex is used to maintain state of child components and update when matches are made.',
            url: 'https://jovial-hypatia-d2fcbc.netlify.com/',
            img: require('../../static/vue-logo.png')
          },
          {
            name: 'React Todo Manager',
            desc:
              'An app that takes down tasks to be completed and has options to remove tasks or mark as completed. A Rails back-end deployed with Heroku acts as the endpoints for the front-end built with React.',
            url: 'https://quizzical-hodgkin-98cdb0.netlify.com/',
            img: require('../../static/react-min.png')
          }
        ],
        length: 0,
        window: 0
      };
    },
    created: function() {
      this.length = this.projects.length;
    },
    methods: {}
  };
</script>