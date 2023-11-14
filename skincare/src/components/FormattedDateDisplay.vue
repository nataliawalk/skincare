
  
  <script setup>
  import { ref, watch } from 'vue'
  import DatePicker from './DatePicker.vue'
  
  const date = ref(null)
  const formattedDate = ref(null);
  const monthNames = [
    "January", "February", "March", "April", "May", "June",
    "July", "August", "September", "October", "November", "December"
  ];
  const dayNames = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'];
  
  const emit = defineEmits(['response'])
  
  watch(date, (newDate) => {
    if (newDate) {
      const selectedDate = new Date(newDate);
      const day = selectedDate.getDay();
      const date = selectedDate.getDate();
      const month = selectedDate.getMonth() + 1;
      const year = selectedDate.getFullYear();
      const monthName = monthNames[month - 1];
      const dayName = dayNames[day];
  
      formattedDate.value = `${dayName} / ${date} / ${month} / ${monthName} / ${year}`;
      emit('response', formattedDate.value); // Emitting formattedDate
    }
  });
  </script>
  
  <template>
    <div>{{ formattedDate }}</div>
  </template>