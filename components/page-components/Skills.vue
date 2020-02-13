<template>
  <div class="skills">
    <div
      v-anime="{
        translateX: [{ value: [-100, 0], duration: 1000, delay: 200 }],
        opacity: [{ value: [0, 1], duration: 1000, delay: 200 }],
        easing: 'easeOutSine(1, .5)',
        loop: false
      }"
    >
      <v-card class="mx-auto text-center" max-width="600">
        <v-row>
          <v-col>
            <v-list :dense="dense">
              <v-list-item-group>
                <v-list-item v-for="(item, i) in items.slice(0, 4)" :key="i">
                  <v-list-item-content>
                    <p class="font-weight-light">{{ item }}</p>
                  </v-list-item-content>
                </v-list-item>
              </v-list-item-group>
            </v-list>
          </v-col>
          <v-col>
            <v-list :dense="dense">
              <v-list-item-group>
                <v-list-item v-for="(item, i) in items.slice(5, 9)" :key="i">
                  <v-list-item-content>
                    <p class="font-weight-light">{{ item }}</p>
                  </v-list-item-content>
                </v-list-item>
              </v-list-item-group>
            </v-list>
          </v-col>
          <v-col>
            <v-list :dense="dense">
              <v-list-item-group>
                <v-list-item v-for="(item, i) in items.slice(10, 15)" :key="i">
                  <v-list-item-content>
                    <p class="font-weight-light">{{ item }}</p>
                  </v-list-item-content>
                </v-list-item>
              </v-list-item-group>
            </v-list>
          </v-col>
        </v-row>
      </v-card>
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      items: [
        'JavaScript (ES6)',
        'TypeScript',
        'Vue JS',
        'Angular JS',
        'React JS',
        'Ruby on Rails',
        'RSpec',
        'Ruby',
        'SQL',
        'HTML & CSS',
        'SCSS/SASS',
        'Node/Express JS',
        'PHP/Laravel',

        'Jest/Chai/Mocha'
      ]
    };
  },
  created: function() {},
  methods: {}
};
</script>
