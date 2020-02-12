<template>
  <div class="skills">
    <v-row id="technologies">
      <!-- <v-col class="text-center" cols="12"> -->
      <v-col cols="12">
        <v-card class="mx-auto" max-width="500">
          <v-list>
            <v-list-item-group>
              <v-list-item
                v-for="(item, i) in items"
                :key="i"
                v-anime="{
                  translateX: [-50, 0],
                  direction: 'alternate',
                  loop: false,
                  delay: function() {
                    return i * 50;
                  },
                  endDelay: function() {
                    return (items.length - i) * 200;
                  }
                }"
              >
                <v-list-item-content>
                  <p class="font-weight-light">{{ item }}</p>
                  <!-- <v-list-item-title v-text="item" /> -->
                </v-list-item-content>
              </v-list-item>
            </v-list-item-group>
          </v-list>
        </v-card>
      </v-col>
    </v-row>
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
          'PHP',
          'Laravel',
          'Jest/Chai/Mocha'
        ]
      };
    },
    created: function() {},
    methods: {}
  };
</script>
