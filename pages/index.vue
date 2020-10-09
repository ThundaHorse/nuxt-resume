<template>
  <div id="home">
    <section id="hero">
        <v-row no-gutters>
          <v-img
            :min-height="'calc(100vh - ' + $vuetify.application.top + 'px)'"
            :src="wallpapers.hero.src"
          >
            <v-theme-provider dark>
              <v-container fill-height>
                <v-row
                  align="center"
                  class="white--text mx-auto"
                  justify="center"
                >
                  <v-col
                    class="white--text text-center"
                    cols="12"
                    tag="h1"
                  >
                    <span
                    :class="[$vuetify.breakpoint.smAndDown ? 'display-1' : 'display-2']"
                      class="font-weight-light"
                    >
                      Hello there, I'm
                    </span>

                    <br>

                    <span
                      :class="[$vuetify.breakpoint.smAndDown ? 'display-3': 'display-4']"
                      class="font-weight-black"
                    >
                      Abraham Kim
                    </span>

                  </v-col>

                  <v-btn
                    class="align-self-end"
                    fab
                    outlined
                    @click="$vuetify.goTo('#about-me')"
                  >
                    <v-icon>mdi-chevron-double-down</v-icon>
                  </v-btn>
                </v-row>
              </v-container>
            </v-theme-provider>
          </v-img>
        </v-row>
      </section>

      <v-divider class="mx-4" />
      <v-btn
        v-scroll="onScroll"
        v-show="fab"
        fab
        dark
        fixed
        bottom
        right
        color="primary"
        @click="toTop"
      >
        <v-icon>
          mdi-chevron-double-up
        </v-icon>
      </v-btn>

      <section id="about-me">
        <v-img
          :min-height="'calc(100vh - ' + $vuetify.application.top + 'px)'"
          :src="wallpapers.about.src"
        >
          <div class="py-12"></div>

          <v-container class="text-center">
            <v-btn
              class="align-self-end"
              fab
              small
              outlined
              @click="$vuetify.goTo('#hero')"
            >
              <v-icon>mdi-chevron-double-up</v-icon>
            </v-btn>

            <h2 class="display-2 mt-4 font-weight-bold mb-3">ABOUT ME</h2>

            <v-responsive
              class="mx-auto mb-8"
              width="56"
            >
              <v-divider class="mb-1" />
              <v-divider />
            </v-responsive>

            <v-responsive
              class="mx-auto title font-weight-light mb-8"
              max-width="720"
            >
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
            </v-responsive>

            <v-avatar
              class="elevation-12 mb-12"
              size="128"
            >
              <v-img :src="abeSelfie.src" :alt="abeSelfie.alt" />
            </v-avatar>

            <div></div>

            <v-row>
                <v-col>
                  <v-btn
                    color="orange accent-2"
                    text
                    href="https://www.github.com/ThundaHorse"
                  >
                    Github
                  </v-btn>
                  <v-btn
                    color="light-blue darken-1"
                    text
                    href="https://www.linkedin.com/in/abrahamtkim/"
                  >
                    LinkedIn
                  </v-btn>
                  <v-btn
                    color="light-green accent-3"
                    text
                    href="https://medium.com/@abekeeem"
                  >
                    Medium
                  </v-btn>
                </v-col>
              </v-row>

              <v-btn
                class="align-self-end"
                fab
                outlined
                small
                @click="$vuetify.goTo('#projects')"
              >
                <v-icon>mdi-chevron-double-down</v-icon>
              </v-btn>
          </v-container>

          <div class="py-12"></div>
        </v-img>
      </section>

      <section id="projects">
        <v-img
          :min-height="'calc(100vh - ' + $vuetify.application.top + 'px)'"
          src=""
        >
          <div class="py-12"></div>

          <v-container class="text-center">
            <v-btn
              class="align-self-end"
              fab
              small
              outlined
              @click="$vuetify.goTo('#about-me')"
            >
              <v-icon>mdi-chevron-double-up</v-icon>
            </v-btn>

            <h2 class="display-2 mt-4 font-weight-bold mb-3">PROJECTS</h2>

            <v-responsive
              class="mx-auto mb-12"
              width="56"
            >
              <v-divider class="mb-1" />
              <v-divider />
            </v-responsive>

            <v-row align="center">
              <v-item-group v-model="window" class="shrink mr-6" mandatory tag="v-flex">
                <v-item
                  v-for="(project, idx) in projects"
                  :key="idx"
                  v-slot:default="{ active, toggle }"
                >
                  <div>
                    <v-btn
                      :input-value="active"
                      icon
                      @click="toggle"
                    >
                      <v-icon>mdi-record</v-icon>
                    </v-btn>
                  </div>
                </v-item>
              </v-item-group>

              <v-col>
                <v-window
                  v-model="window"
                  class="elevation-1"
                  vertical
                >
                  <v-window-item
                    v-for="(project, idx) in projects"
                    :key="idx"
                  >
                    <v-card flat>
                      <v-card-text>
                        <v-row
                          class="mb-4"
                          align="center"
                        >
                          <v-avatar
                            class="mr-4"
                          >
                            <v-img :src="project.src" />
                          </v-avatar>
                          <strong class="title">{{ project.name }}</strong>
                          <v-spacer></v-spacer>
                          <div v-if="project.url2">
                            <v-btn outlined rounded small icon>
                              <a :href="project.url" target="_blank" style="color: white; text-decoration: none;">
                                F
                              </a>
                            </v-btn>
                            <v-btn outlined rounded small icon>
                              <a :href="project.url2" target="_blank" style="color: white; text-decoration: none;">
                                B
                              </a>
                            </v-btn>
                          </div>
                          <div v-else>
                            <v-btn outlined rounded small icon>
                              <a :href="project.url" target="_blank" style="color: white; text-decoration: none;">
                                &lt;/&gt;
                              </a>
                            </v-btn>
                          </div>
                        </v-row>
                        <p>
                          {{ project.desc }}
                        </p>
                      </v-card-text>
                    </v-card>
                  </v-window-item>
                </v-window>
              </v-col>
            </v-row>

            <v-btn
              class="align-self-end mt-4"
              fab
              small
              outlined
              @click="$vuetify.goTo('#blog')"
            >
              <v-icon>mdi-chevron-double-down</v-icon>
            </v-btn>
          </v-container>

          <div class="py-12"></div>
        </v-img>
      </section>

      <v-divider class="mx-4" />

      <section id="blog">
        <v-img
          :min-height="'calc(100vh - ' + $vuetify.application.top + 'px)'"
          :src="wallpapers.about.src"
        >
          <div class="py-6"></div>

          <v-container class="text-center">
            <v-btn
              class="align-self-end"
              fab
              small
              outlined
              @click="$vuetify.goTo('#projects')"
            >
              <v-icon>mdi-chevron-double-up</v-icon>
            </v-btn>

            <h2 class="display-2 mt-4 font-weight-bold mb-3 text-uppercase text-center">Blog</h2>

            <v-responsive
              class="mx-auto mb-12"
              width="56"
            >
              <v-divider class="mb-1"></v-divider>

              <v-divider></v-divider>
            </v-responsive>

            <v-row>
              <v-col
                v-for="({ src, text, title }, i) in articles"
                :key="i"
                cols="12"
                md="4"
                lg="4"
              >
                <v-card class="mx-auto my-4" elevation="2" outlined shaped>
                  <v-card-title>
                    <h3 class="font-weight-black mb-4" v-text="title" />
                  </v-card-title>

                  <v-divider class="mx-4" />

                  <v-card-text>
                    <div class="title font-weight-light mb-5" v-text="text" />
                  </v-card-text>

                  <v-divider class="mx-4" />

                  <v-card-actions>
                    <v-btn class="font-weight-black" text>
                      <a :href="src" target="_blank" style="text-decoration: none;">
                        CONTINUE READING
                      </a>
                    </v-btn>
                  </v-card-actions>
                </v-card>
              </v-col>
            </v-row>

            <v-btn
              class="align-self-end"
              fab
              small
              outlined
              @click="$vuetify.goTo('#stats')"
            >
              <v-icon>mdi-chevron-double-down</v-icon>
            </v-btn>
          </v-container>

          <div class="py-12"></div>
        </v-img>
      </section>

      <v-divider class="mx-4" />

      <section id="stats">
        <v-parallax
          :height="$vuetify.breakpoint.smAndDown ? 700 : 500"
          src="https://images.unsplash.com/photo-1510915228340-29c85a43dcfe?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1950&q=80"
        >
          <v-container>
            <h2 class="display-2 font-weight-bold mb-3 text-uppercase text-center">Skills</h2>

            <v-responsive
              class="mx-auto mb-12"
              width="56"
            >
              <v-divider class="mb-1"></v-divider>

              <v-divider></v-divider>
            </v-responsive>

            <v-row class="mx-auto">
              <v-col
                v-for="(tool, idx) of tools"
                :key="idx"
                cols="12"
                md="3"
              >
                <div class="text-center">
                  <v-progress-circular :value="tool.val" :color="tool.color" size="70" width="7" />
                  <div
                    class="title font-weight-regular text-uppercase"
                    v-text="tool.name"
                  ></div>
                </div>
              </v-col>
            </v-row>
          </v-container>
        </v-parallax>
      </section>

      <v-divider class="mx-4" />

      <!-- <v-sheet
        id="contact"
        color="#333333"
        dark
        tag="section"
        tile
      >
        <div class="py-12"></div>

        <v-container>
          <h2 class="display-2 font-weight-bold mb-3 text-uppercase text-center">Contact Me</h2>

          <v-responsive
            class="mx-auto mb-12"
            width="56"
          >
            <v-divider class="mb-1"></v-divider>

            <v-divider></v-divider>
          </v-responsive>

          <v-theme-provider light>
            <v-row>
              <v-col cols="12">
                <v-text-field
                  flat
                  label="Name*"
                  solo
                ></v-text-field>
              </v-col>

              <v-col cols="12">
                <v-text-field
                  flat
                  label="Email*"
                  solo
                ></v-text-field>
              </v-col>

              <v-col cols="12">
                <v-text-field
                  flat
                  label="Subject*"
                  solo
                ></v-text-field>
              </v-col>

              <v-col cols="12">
                <v-textarea
                  flat
                  label="Message*"
                  solo
                ></v-textarea>
              </v-col>

              <v-col
                class="mx-auto"
                cols="auto"
              >
                <v-btn
                  color="accent"
                  x-large
                >
                  Submit
                </v-btn>
              </v-col>
            </v-row>
          </v-theme-provider>
        </v-container>

        <div class="py-12"></div>
      </v-sheet> -->
  </div>
</template>

<script>
  export default {
    data () {
      return {
        abeSelfie: {
          src: require('@/static/abeBayern.jpg'),
          alt: "Abe Selfie"
        },
        wallpapers: {
          hero: {
            src: require("@/static/heroWallpaper.jpg"),
            alt: "Hero"
          },
          about: {
            src: require("@/static/aboutWallpaper.jpg"),
            alt: "About"
          }
        },
        articles: [
          {
            src: 'https://medium.com/@abekeeem/a-tale-of-two-databases-f0bdd44a6263',
            title: 'A Tale of two Databases',
            text: 'A challenge I had to overcome during my coding bootcamp'
          },
          {
            src: 'https://medium.com/@abekeeem/finding-the-longest-connected-islands-7ab77c95d41d',
            title: 'Connected Islands',
            text: 'My reflection on a coding challenge that took me for a spin',
          },
          {
            src: 'https://medium.com/@abekeeem/generating-generators-8e53b60298f1',
            title: 'Generating Generators?',
            text: 'Takeaways from generator functions',
          },
          {
            src: 'https://medium.com/@abekeeem/getting-to-know-aws-84105fd61d76',
            title: 'Getting to know AWS',
            text: 'A brief reflection on AWS and my initial thoughts',
          }
        ],
        projects: [
        {
          name: "Our Daily Memes",
          desc:
            'Users can sign up for accounts or browser without an account. Users can post memes and a short description of their meme. Images are stored in AWS. The back-end is built with Ruby on Rails and a Vue.JS Front-end. Each post has individual likes/dislikes and comments. Users can comment on a post and see their comments in real-time.',
          url: 'https://ourdailymemes.netlify.app/',
          src: require('@/static/memes.png')
        },
        {
          name: "Mock E-Commerce App",
          desc:
            'Users are required to sign in to view their postings. Items can have multiple attached images, made possible with AWS. Each item page features a chat box for inquiries. Currently still under construction for addition of dummy payment features.',
          url: 'https://compassionate-wilson-a34cfc.netlify.app/',
          src: require('@/static/ecommerce.png')
        },
        {
          name: "Let's go to Disney",
          desc:
            'An app designed to help users create and keep tabs on a trip for Disney. In addition to creating an itinerary to plan a day at Disney, attraction wait times are updated in real-time by utilizing Action Cable and custom rake tasks in Rails that utilizes a custom script to be run at set intervals. in conjunction with the API to gather times, the script file access the Rails database and updates the attraction models which in turn is updated in the Vue app by Action Cable.',
          url: 'https://github.com/ThundaHorse/disney_vue_app',
          url2: 'https://github.com/ThundaHorse/disney_app',
          src: require('@/static/disney.jpg')
        },
        {
          name: 'Vuex Memory Game',
          desc:
            'A user can choose two cards and if they match, they stay unflipped and your score goes up! Vuex is used to maintain state of child components and update when matches are made.',
          url: 'https://jovial-hypatia-d2fcbc.netlify.app/',
          src: require('@/static/vuex.png')
        },
        {
          name: 'React Todo Manager',
          desc: 'An app that takes down tasks to be completed and has options to remove tasks or mark as completed. A Rails back-end deployed with Heroku acts as the endpoints for the front-end built with React.',
          url: 'https://quizzical-hodgkin-98cdb0.netlify.app/',
          src: require('@/static/reactTodo.png')
        }
      ],
        length: 0,
        window: 0,
        tools: [
          {
            name: "Vue",
            val: "80",
            color: "teal accent-3"
          },
          {
            name: "React",
            val: "70",
            color: "cyan lighten-2"
          },
          {
            name: "Angular",
            val: "40",
            color: "red"
          },
          {
            name: "Ruby on Rails",
            val: "80",
            color: "red darken-4"
          },
          {
            name: "Laravel",
            val: "60",
            color: "orange-darken-2"
          },
          {
            name: "SQL",
            val: "80",
            color: "blue lighten-2"
          },
          {
            name: "Ruby",
            val: "75",
            color: "red darken-2"
          },
          {
            name: "JavaScript",
            val: "85",
            color: "yellow-accent-2"
          },
          {
            name: "TypeScript",
            val: "70",
            color: "light-blue accent-3"
          },
          {
            name: "Node",
            val: "75",
            color: "green darken-1"
          },
          {
            name: "PHP",
            val: "60",
            color: "deel purple lighten-3"
          },
          {
            name: "HTML/CSS3/SCSS",
            val: "90",
            color: "lime accent-3"
          }
        ],
        fab: false
      }
    },
    created: function() {
      this.length = this.projects.length;
    },
    methods: {
      onScroll (e) {
        if (typeof window === 'undefined') return
        const top = window.pageYOffset ||   e.target.scrollTop || 0
        this.fab = top > 20
      },
      toTop () {
        this.$vuetify.goTo(0)
      }
    }
  }
</script>