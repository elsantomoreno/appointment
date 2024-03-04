<script setup>
import CardContainer from './components/Appointment/CardContainer.vue'
const today = new Date()
const yyyy = today.getFullYear()
let mm = today.getMonth() + 1 // Months start at 0!
let dd = today.getDate()

if (dd < 10) dd = '0' + dd
if (mm < 10) mm = '0' + mm

const formattedToday = dd + '.' + mm + '.' + yyyy
</script>

<template>
  <div class="card-app">
    <h1 style="font-weight: bold">Welcome to Opportunity</h1>
    <h2 class="datevalue">{{ formattedToday }}</h2>

    <CardContainer></CardContainer>
  </div>
</template>
<style scoped>
.card-app {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.datevalue {
  width: 370px;
}
h1 {
  justify-content: start;
  align-items: start;
  width: 370px;
}
</style>
