<script setup>
import { defineProps } from 'vue'
defineProps({
  time: {
    type: String,
    required: true
  },

  date: {
    type: String,
    required: true
  },
  title: {
    type: String,
    required: true
  },
  event: {
    type: String,
    required: true
  }
})
</script>
<template>
  <div class="superdiv">
    <div class="card-date">
      <p class="date">{{ time }},{{ date }}</p>
      <h2 class="title">{{ title }}</h2>
      <p class="subject">{{ event }}</p>
    </div>
    <div></div>
  </div>
</template>
<style scoped>
.card-date {
  display: flex;
  flex-direction: column;
  align-items: start;
  justify-content: center;
  background-color: #2f2fe9;
  width: 370px;
  padding: 10px;
}
.date {
  color: rgb(222, 16, 16);
  font-weight: bold;
  font-size: 20px;
}
.superdiv {
  margin-top: 10px;
  background-color: white;
}
.title {
  color: antiquewhite;
}
.subject {
  color: rgb(170, 212, 249);
}
</style>
