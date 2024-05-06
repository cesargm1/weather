<template>
    <main class="wather"></main>
    <button @click="callApi">buscar</button>
    <input v-if="response">{{ response }}<input>
</template>

<script setup>
import {ref} from 'vue';

const country = ref("")

const response = ref("")

const callApi =  async () => {
    const responsehttp = await fetch("https://api.open-meteo.com/v1/forecast?latitude=52.52&longitude=13.41&hourly=temperature_2m/" + country.value)
    responsehttp.value = await responsehttp.json();
}

</script>


<style scoped></style>