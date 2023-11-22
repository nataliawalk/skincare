<script setup>
import { ref, watch } from 'vue'

const date = ref(null)
const formattedDate = ref(null);
const monthNames = ["January", "February", "March", "April", "May", "June",
  "July", "August", "September", "October", "November", "December"
];
const dayNames = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'];

watch(date, (newDate) => {
  if (newDate) {
    const selectedDate = new Date(newDate);
    const day = selectedDate.getDay();
    const date = selectedDate.getDate();
    const month = selectedDate.getMonth()+1;
    const year = selectedDate.getFullYear();
    const monthName = monthNames[month];
    const dayName = dayNames[day];

    formattedDate.value = `${dayName} / ${date} / ${month} / ${monthName} /${year}`;
  }
});
</script>

<template>
    <div>{{formattedDate}}</div>
        
    <v-container>
    <v-row justify="space-around">
        <v-date-picker v-model="date" elevation="6" ></v-date-picker>
    </v-row>
    </v-container>
</template>