<template>
  <v-layout column justify-center align-center>
    <v-row id="intro" align="center" justify="center">
      <v-col class="text-center" cols="12">
        <h1 class="display-1 font-weight-regular mb-4">Hi there!</h1>
        <h4 class="subheading font-weight-regular">
          My name is Abraham Kim. I put pieces of the web together. I'm a
          software engineer who crafts precise and aesthetically pleasing web
          apps. Exploring new languages and frameworks is what I enjoy among
          many other things. I like to focus on making sure my work is
          thouroughly tested and fit to be scaled and maintained. Honing my
          skills to create efficient and concise code is my goal.
        </h4>
      </v-col>      
    </v-row>
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
    <v-row id="technologies" align="center" justify="center">
      <v-col class="text-center" cols="4">
        <ul style="list-style: none;">
          <li>
            Javascript (ES6)
          </li>
          <li>VueJS</li>
          <li>React</li>
          <li>Ruby Ruby on Rails</li>
        </ul>
      </v-col>
      <v-col class="text-center" cols="4">
        <ul style="list-style: none;">
          <li>
            SQL
          </li>
          <li>Express</li>
          <li>TypeScript HTML & CSS</li>
          <li>Node.Js</li>
        </ul>
      </v-col>
      <v-col class="text-center" cols="4">
        <ul style="list-style: none;">
          <li>PHP</li>
          <li>Laravel</li>
          <li>RSpec/Minitest</li>
          <li>Jest/Chai/Mocha</li>
        </ul>
      </v-col>
    </v-row>
    <v-row id="projects" align="center" justify="center">
      <v-col class="text-center" cols="12">
        <v-card ripple="true"
                :light="idx % 2 !== 0"
                elevation="10"
                max-width="344"
                class="mx-auto"
                v-for="(project, idx) in projects"
                :key="idx">
          <v-list-item>
            <!-- <v-list-item-avatar color="grey"></v-list-item-avatar> -->
            <v-list-item-content>
              <v-list-item-title class="headline">
                {{
                project.name
                }}
              </v-list-item-title>
              <!-- <v-list-item-subtitle>by Kurt Wagner</v-list-item-subtitle> -->
            </v-list-item-content>
          </v-list-item>

          <v-img src="https://cdn.vuetifyjs.com/images/cards/mountain.jpg"
                 height="194"></v-img>

          <v-card-text>
            {{ project.desc }}
          </v-card-text>

          <v-card-actions>
            <!-- <v-btn text color="deep-purple accent-4">
              Read
            </v-btn>
            <v-btn text color="deep-purple accent-4">
              Bookmark
            </v-btn> -->
            <v-spacer></v-spacer>
            <v-btn icon :href="project.url">
              <v-hover>
                <v-icon>mdi-heart</v-icon>
              </v-hover>
            </v-btn>
            <v-btn icon>
              <v-hover>
                <v-icon>mdi-share-variant</v-icon>
              </v-hover>
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-layout>
</template>

<script>
  export default {
    data: function () {
      return {
        message:
          'Sawyer and Associates, pending civil matter, 866-515-0247, Sang Myung Kim, answer any questions he/she asks, Ref num: 405060',
        projects: [
          {
            name: "Let's go to Disney",
            desc:
              'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum',
            url: 'https://www.github.com/ThundaHorse'
          },
          {
            name: 'Tripper',
            desc:
              'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum',
            url: 'https://www.github.com/ThundaHorse'
          },
          {
            name: 'Vue Memory Game',
            desc:
              'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum',
            url: 'https://www.github.com/ThundaHorse'
          }
        ]
      }
    }
  }
</script>
