<script setup>
import { ref } from 'vue';

const tab = ref('Routine');
const items = ref(['Routine', 'Your Stash', 'Templates', 'Tips']);
const text = 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.';

import { useTheme } from 'vuetify'
const theme = useTheme()
const toggleTheme = () => {
  theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
}

const darkModeIcon = ref(false);
const toggleDarkModeIcon = () => {
  darkModeIcon.value = !darkModeIcon.value;
}

const toggleDarkMode = () => {
  toggleTheme();
  toggleDarkModeIcon();
}

</script>

<template>


      <v-app-bar :elevation="0" >

          <!-- <v-btn prepend-icon="mdi-calendar">
            today
            <v-icon icon="mdi-chevron-down" />
          </v-btn> -->

          <v-btn icon="mdi-calendar"></v-btn>
        
          <v-app-bar-title class="font-weight-bold font-italic header-title text-center">Skincare.</v-app-bar-title>
          
          <v-btn icon 
          @click="toggleDarkMode"
          >
            <span v-if="darkModeIcon" class="material-symbols-outlined">light_mode</span>
            <span v-else class="material-symbols-outlined">dark_mode</span>
          </v-btn>

      </v-app-bar>


      <v-tabs
        v-model="tab"
        align-tabs="center"
        height="100"

      >
        <v-tab
          v-for="item in items"
          :key="item"
          :value="item"
          min-width="250"
          class="text-none"
          height="160"
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
.v-btn {
    letter-spacing: 0.05em;
    font-weight: 400;    
}

.v-tab--selected {
    font-weight: 500;
}

</style>