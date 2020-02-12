<template>
  <div class="projects">
    <v-row id="projects" align="center" justify="center">
      <v-col class="text-center" cols="12">
        <v-card
          :ripple="true"
          :light="idx % 2 !== 0"
          elevation="10"
          max-width="344"
          class="mx-auto"
          v-for="(project, idx) in projects"
          :key="idx"
        >
          <v-list-item>
            <!-- <v-list-item-avatar color="grey"></v-list-item-avatar> -->
            <v-list-item-content>
              <v-list-item-title class="headline">{{
                project.name
              }}</v-list-item-title>
              <!-- <v-list-item-subtitle>by Kurt Wagner</v-list-item-subtitle> -->
            </v-list-item-content>
          </v-list-item>

          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/mountain.jpg"
            height="194"
          ></v-img>

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
  </div>
</template>

<script>
export default {
  data: function() {
    return {
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
    };
  },
  created: function() {},
  methods: {}
};
</script>