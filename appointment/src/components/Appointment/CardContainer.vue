<script setup>
import CardComponent from './CardComponent.vue'
const sheet_id = import.meta.env.VITE_GOOGLE_SHEET_ID
const api_token = import.meta.env.VITE_GOOGLE_API_KEY
import { ref } from 'vue'
let fullData = ref('')
let url = `https://sheets.googleapis.com/v4/spreadsheets/${sheet_id}/values:batchGet?ranges=A2%3AE100&valueRenderOption=FORMATTED_VALUE&key=${api_token}`
async function fetchData() {
  const response = await fetch(url)
  const data = await response.json()
  fullData.value = data.valueRanges[0].values
}

fetchData()
</script>
<template>
  <CardComponent
    v-for="(result, key) in fullData"
    :key="key"
    :time="result[0]"
    :date="result[1]"
    :event="result[2]"
    :title="result[3]"
  >
  </CardComponent>
</template>
