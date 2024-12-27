<template>
  <div id="home">
    <section id="hero">
      <v-row no-gutters>
        <v-img
          :min-height="'calc(100vh - ' + $vuetify.application.top + 'px)'"
          :src="wallpapers.hero.src"
        >
          <v-theme-provider>
            <v-container fill-height>
              <v-row
                align="center"
                class="white--text mx-auto"
                justify="center"
              >
                <v-col class="white--text text-center" cols="12" tag="h1">
                  <span
                    :class="[
                      $vuetify.breakpoint.smAndDown ? 'display-1' : 'display-2'
                    ]"
                    class="font-weight-light"
                  >
                    Hello there, I'm
                  </span>

                  <br />

                  <span
                    :class="[
                      $vuetify.breakpoint.smAndDown ? 'display-3' : 'display-4'
                    ]"
                    class="font-weight-black"
                  >
                    Abraham Kim
                  </span>
                </v-col>

                <v-btn
                  class="align-self-end mt-8"
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
        class="about-wallpaper"
      >
        <div class="py-12"></div>

        <v-container class="text-center">
          <div v-if="!isMobile">
            <v-btn
              class="align-self-end"
              fab
              small
              outlined
              @click="$vuetify.goTo('#hero')"
            >
              <v-icon>mdi-chevron-double-up</v-icon>
            </v-btn>
          </div>

          <h2 class="display-2 mt-8 font-weight-bold mb-2">ABOUT ME</h2>

          <v-responsive class="mx-auto mb-4" width="56">
            <v-divider class="mb-1" />
            <v-divider />
          </v-responsive>

          <v-responsive
            class="mx-auto title font-weight-light mb-8"
            max-width="720"
          >
            Hi! I'm a Full-Stack Developer!
            <br />
            I graduated from Georgia State University with a degree in Political
            Science.
            <br />
            I have always intruigued by software development and taught myself
            Javascript and Ruby throughout my undergraduate studies.

            <br />
            <br />
            In 2019 I decided to attend Actualize Coding Bootcamp in Chicago, IL
            to pursue my passion.
            <br />
            <br />
            When I am not immersing myself in best practices, or finding neat
            tricks to optimize my work you can often find me at the MMA gym
            continuing my MMA training!
            <br />
            <br />
            With a full-stack background, navigation from back end to front end
            comes naturally. I am constantly honing my skills so that any areas
            of uncertainty can be remedied.
          </v-responsive>

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
            v-if="!isMobile"
            class="align-self-end mt-8"
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
        class="projects-wallpaper"
      >
        <div class="py-12"></div>

        <v-container class="text-center">
          <div v-if="!isMobile">
            <v-btn
              class="align-self-end"
              fab
              small
              outlined
              @click="$vuetify.goTo('#about-me')"
            >
              <v-icon>mdi-chevron-double-up</v-icon>
            </v-btn>
          </div>

          <h2 class="display-2 mt-8 font-weight-bold mb-3">PROJECTS</h2>

          <v-responsive class="mx-auto mb-8" width="56">
            <v-divider class="mb-1" />
            <v-divider />
          </v-responsive>

          <v-row align="center">
            <v-item-group
              v-model="window"
              class="shrink mr-6"
              mandatory
              tag="v-flex"
            >
              <v-item
                v-for="(project, idx) in projects"
                :key="idx"
                v-slot:default="{ active, toggle }"
              >
                <div>
                  <v-btn :input-value="active" icon @click="toggle">
                    <v-icon>mdi-record</v-icon>
                  </v-btn>
                </div>
              </v-item>
            </v-item-group>

            <v-col>
              <v-window v-model="window" class="elevation-1" vertical>
                <v-window-item v-for="(project, idx) in projects" :key="idx">
                  <v-card flat>
                    <v-card-text>
                      <v-row class="mb-4" align="center">
                        <v-avatar class="mr-4">
                          <v-img :src="project.src" />
                        </v-avatar>
                        <strong class="title">{{ project.name }}</strong>
                        <v-spacer></v-spacer>
                        <div v-if="project.url2">
                          <v-btn outlined rounded small icon>
                            <a
                              :href="project.url"
                              target="_blank"
                              style="color: white; text-decoration: none;"
                            >
                              F
                            </a>
                          </v-btn>
                          <v-btn outlined rounded small icon>
                            <a
                              :href="project.url2"
                              target="_blank"
                              style="color: white; text-decoration: none;"
                            >
                              B
                            </a>
                          </v-btn>
                        </div>
                        <div v-else>
                          <v-btn outlined rounded small icon>
                            <a
                              :href="project.url"
                              target="_blank"
                              style="color: white; text-decoration: none;"
                            >
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
            v-if="!isMobile"
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

    <section id="blog">
      <v-img
        :min-height="'calc(100vh - ' + $vuetify.application.top + 'px)'"
        src=""
        class="blog-wallpaper"
      >
        <div class="py-12"></div>

        <v-container class="text-center">
          <div v-if="!isMobile">
            <v-btn
              class="align-self-end"
              fab
              small
              outlined
              @click="$vuetify.goTo('#projects')"
            >
              <v-icon>mdi-chevron-double-up</v-icon>
            </v-btn>
          </div>

          <h2
            class="display-2 mt-8 font-weight-bold mb-3 text-uppercase text-center"
          >
            Blog
          </h2>

          <v-responsive class="mx-auto mb-12" width="56">
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
                    <a
                      :href="src"
                      target="_blank"
                      style="text-decoration: none;"
                    >
                      CONTINUE READING
                    </a>
                  </v-btn>
                </v-card-actions>
              </v-card>
            </v-col>
          </v-row>

          <v-btn
            v-if="!isMobile"
            class="align-self-end mt-8"
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

    <section id="stats">
      <v-img
        :min-height="'calc(100vh - ' + $vuetify.application.top + 'px)'"
        src=""
        class="stats-wallpaper"
      >
        <v-container class="skills-area text-center">
          <v-row class="mx-auto">
            <v-col cols="12">
              <div class="skills-intro">
                <div v-if="!isMobile">
                  <v-btn
                    class="align-self-end"
                    fab
                    small
                    outlined
                    @click="$vuetify.goTo('#blog')"
                  >
                    <v-icon>mdi-chevron-double-up</v-icon>
                  </v-btn>
                </div>
                <h2
                  class="display-2 font-weight-bold mt-8 mb-3 text-uppercase text-center"
                >
                  Skills
                </h2>
              </div>
            </v-col>
          </v-row>

          <v-row class="mx-auto skills-display">
            <v-col v-for="(tool, idx) of tools" :key="idx" cols="12" md="3">
              <div class="text-center">
                <v-progress-circular
                  :value="tool.val"
                  :color="tool.color"
                  size="70"
                  width="7"
                />
                <div
                  class="title font-weight-regular text-uppercase"
                  v-text="tool.name"
                ></div>
              </div>
            </v-col>
          </v-row>
        </v-container>
      </v-img>
    </section>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        wallpapers: {
          hero: {
            src: require('@/static/about-wallpaper.webp'),
            alt: 'Hero'
          },
          about: {
            src: require('@/static/hero-section-wallpaper.webp'),
            alt: 'About'
          },
          blog: {
            alt: 'Blog'
          },
          stats: {
            alt: 'Stats'
          }
        },
        articles: [
          {
            src:
              'https://medium.com/@abekeeem/a-tale-of-two-databases-f0bdd44a6263',
            title: 'A Tale of two Databases',
            text: 'A challenge I had to overcome during my coding bootcamp'
          },
          {
            src:
              'https://medium.com/@abekeeem/finding-the-longest-connected-islands-7ab77c95d41d',
            title: 'Connected Islands',
            text: 'My reflection on a coding challenge that took me for a spin'
          },
          {
            src:
              'https://medium.com/@abekeeem/generating-generators-8e53b60298f1',
            title: 'Generating Generators?',
            text: 'Takeaways from generator functions'
          },
          {
            src:
              'https://medium.com/@abekeeem/getting-to-know-aws-84105fd61d76',
            title: 'Getting to know AWS',
            text: 'A brief reflection on AWS and my initial thoughts'
          }
        ],
        projects: [
          {
            name: 'Young & Company ',
            desc:
              'Freelance project which entailed building a efficient and SEO friendly website for tax accountant. Achieved with Vite + React.js as well as Tailwind CSS in conjunction with Flowbite. Decision to utilize Flowbite was influenced by most components being open source and repretoire of advanced components. Vite was utilized due to its nature of being an independent tool for building and bundling. Vite significantly outperformed Webpack and useage of its inherit ES Module imports was a learning curve but delivered an efficient website and weighed in on design patterns and overall layout.',
            url: 'https://youngcotax.com',
            src: require('@/static/youngcotax.webp')
          },
          {
            name: 'Waximo',
            desc:
              'Freelance project for building a website for a startup focusing on an innovative, cost-effective, time-saving, all-in-one tool that simplifies the waxing process for you to spend less time maintaining your snowboard or ski equipment and more time on the slopes. Built with NextJS + TypeScript, efficiently serves up a single page application with capabilities such as sign up, refer others, and a contact form without setting up a backend. In place of the backend, Google Sheets was used and scripts were made to send form data to Google Sheets where the data was recorded. Deployed via Netlify, hosting and environment variable management was streamlined and continuous deployments + NextJS build images ensure failures are known before going live.',
            url: 'https://waximo.com',
            src: require('@/static/waximologo.png')
          },
          {
            name: 'Statefarm Search',
            desc:
              "Utilized Vue3 & Vite to restructure Statefarm's search UI. Terraform and AWS was utilized to move legacy backend to a modern cloud first approach. Assisted in planning and implementation of UI and setting up backend.",
            url: 'https://search.c1.statefarm/',
            src: require('@/static/redSearch.png')
          },
          {
            name: 'Follow the Nerd',
            desc:
              'Professional site completed as a freelance project. Utilizing React JS along with Google Calendar API integration as well as Google review data. Migrated from PorkBun to a faster, smoother, and optimized web app. Services included scheduling appintments and fetching real time business review data and displaying as the client saw fit. In addition to utilizing React hooks and acting as the SME, advised client on functionality and advised in areas where ambiguity was present. Assisted client in optimizing SEO and registering business with Google. Deployed site via Netlify and assisted client in registering custom URL for business needs.',
            url: 'https://followthenerd.com/',
            src: require('@/static/superhero-about-us.svg')
          },
          {
            name: 'Our Daily Memes',
            desc:
              'Users can sign up for accounts or browser without an account. Users can post memes and a short description of their meme. Images are stored in AWS. The back-end is built with Ruby on Rails and a Vue.JS Front-end. Each post has individual likes/dislikes and comments. Users can comment on a post and see their comments in real-time.',
            url: 'https://ourdailymemes.netlify.app/',
            src: require('@/static/memes.png')
          },
          {
            name: 'Mock E-Commerce App',
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
          }
        ],
        length: 0,
        window: 0,
        tools: [
          {
            name: 'Vue',
            val: '80',
            color: 'teal accent-3'
          },
          {
            name: 'React',
            val: '85',
            color: 'cyan lighten-2'
          },
          {
            name: 'Angular',
            val: '75',
            color: 'red'
          },
          {
            name: 'Ruby on Rails',
            val: '75',
            color: 'red darken-4'
          },
          {
            name: 'Laravel',
            val: '60',
            color: 'orange-darken-2'
          },
          {
            name: 'SQL',
            val: '85',
            color: 'blue lighten-2'
          },
          {
            name: 'Ruby',
            val: '80',
            color: 'red darken-2'
          },
          {
            name: 'JavaScript',
            val: '95',
            color: 'yellow-accent-2'
          },
          {
            name: 'TypeScript',
            val: '80',
            color: 'light-blue accent-3'
          },
          {
            name: 'Node',
            val: '75',
            color: 'green darken-1'
          },
          {
            name: 'PHP',
            val: '60',
            color: 'deel purple lighten-3'
          },
          {
            name: 'HTML/CSS3/SCSS',
            val: '95',
            color: 'lime accent-3'
          }
        ],
        fab: false,
        isMobile: false
      };
    },
    created: function() {
      this.length = this.projects.length;
    },
    computed: {
      windowWidth() {
        if (process.client) {
          return window.innerWidth;
        } else {
          return null;
        }
      }
    },
    mounted() {
      this.onResize();

      window.addEventListener('resize', this.onResize, { passive: true });
    },
    beforeDestroy() {
      if (typeof window === 'undefined') return;

      window.removeEventListener('resize', this.onResize, { passive: true });
    },
    methods: {
      onScroll(e) {
        if (typeof window === 'undefined') return;
        const top = window.pageYOffset || e.target.scrollTop || 0;
        this.fab = top > 20;
      },

      onResize() {
        this.isMobile = window.innerWidth < 600;
      },

      toTop() {
        this.$vuetify.goTo(0);
      }
    }
  };
</script>

<style>
  main {
    background-color: black;
  }
  .skills-intro {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 36px;
  }

  .skills-area {
    margin-top: 36px;
  }

  .skills-display {
    margin-top: 36px;
  }

  #hero {
    .v-responsive__content {
      background-size: cover;
      background-repeat: no-repeat;
      background-position: center;
    }
  }

  #about-me {
    .about-wallpaper {
      align-items: center;
    }
  }

  #projects {
    .projects-wallpaper {
      align-items: center;
      background: url('../static/hero-wallpaper-flipped.webp');
      background-repeat: no-repeat;
      background-size: cover;
    }
  }

  #blog {
    .blog-wallpaper {
      align-items: center;
      background: url('../static/blog-wallpaper.webp');
      background-repeat: no-repeat;
      background-size: cover;
    }
  }

  #stats {
    .stats-wallpaper {
      align-items: center;
      background: url('../static/skills-wallpaper.webp');
      background-repeat: no-repeat;
      background-size: cover;
      background-position: 0px -75px;
    }
  }

  @media only screen and (max-width: 768px) {
    .skills-area {
      margin-top: 24px;
    }
  }
</style>
