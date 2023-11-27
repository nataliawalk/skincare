<script setup>
import { ref } from 'vue'
import { useTheme } from 'vuetify'

const theme = useTheme()
const darkModeIcon = ref(false);

const toggleTheme = () => {
  theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
}
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
</template>