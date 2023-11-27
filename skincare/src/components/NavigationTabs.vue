<script setup>
import { ref } from 'vue';

const tab = ref('Routine');
const items = ref(['Routine', 'Your Stash', 'Templates', 'Tips']);
const text = 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.';
</script>


<template>
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