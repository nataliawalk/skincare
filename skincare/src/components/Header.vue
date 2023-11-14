<script setup>
import { ref } from 'vue';

import FormattedDateDisplay from './FormattedDateDisplay.vue'

const tab = ref('Routine');
const items = ref(['Routine', 'Your Stash', 'Templates', 'Tips']);
const text = 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.';

const childMsg = ref('No child msg yet')

</script>

<template>
    <header>
        <div class="navbar">
        <v-btn prepend-icon="mdi-calendar" variant="plain">
            today
            <v-icon icon="mdi-chevron-down" />
        </v-btn>
        <h1 class="font-weight-bold font-italic header-text">
            Skincare.
        </h1>
        </div>
    </header>

    <FormattedDateDisplay @response="(msg) => childMsg = msg" />
    <p>{{ childMsg }}</p>


      <v-tabs
        v-model="tab"
        align-tabs="center"
      >
        <v-tab
          v-for="item in items"
          :key="item"
          :value="item"
          min-width="250"
          class="text-none"
        >
          {{ item }}
        </v-tab>
      </v-tabs>
      
      <v-divider></v-divider>

      <v-window v-model="tab">
        <v-window-item
          v-for="item in items"
          :key="item"
          :value="item"
        >
          <v-card flat>
            <v-card-text>{{ text }}</v-card-text>
          </v-card>
        </v-window-item>
      </v-window>

</template>
  
<style scoped>
.navbar {
    display: flex;
    /* justify-content: space-between; */
    align-items: center;
    margin: 0 1em;
}
.header-text {
    font-family: 'Inter', sans-serif;
    text-align: center;
    margin: 0.4em 0;
    margin-left: auto;
    margin-right: auto;
}
.v-btn {
    letter-spacing: 0.05em;
    font-weight: 400;    
}

.v-tab--selected {
    font-weight: 500;
}

</style>