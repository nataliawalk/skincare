<script setup>
import { ref} from 'vue'

import Header from './components/Header.vue'
import DatePicker from './components/DatePicker.vue'

const childMsg = ref('No child msg yet')

</script>

<template>

  <Header />

  <DatePicker />




      

    <v-container class="text-center">
      <v-row justify="center"> 
        <v-col cols="12" sm="6" md="4">
          <v-btn block rounded="lg" size="x-large">Rounded lg</v-btn>
        </v-col>
        <v-col cols="12" sm="6" md="4">
          <v-btn block rounded="xl" size="x-large" color="red">Rounded xl</v-btn>
        </v-col>
      </v-row>
    </v-container>





</template>

