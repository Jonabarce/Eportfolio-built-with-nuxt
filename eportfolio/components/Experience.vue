<template>
  <div class="experience-wrapper">
    <h1>Experience</h1>
    <div
      class="experience-card"
      v-for="(items, index) in projectData.ExperienceArray"
      v-bind:key="items"
    >
      <h2>{{ projectData.ExperienceArray[index].Title }}</h2>
      <p>{{ projectData.ExperienceArray[index].Company }}</p>
      <p>{{ projectData.ExperienceArray[index].Date }}</p>
      <p>{{ projectData.ExperienceArray[index].About }}</p>
    </div>
  </div>
</template>

<script setup>
import { reactive } from 'vue'
import jsonData from '@/experience.json'

const projectData = reactive(jsonData)
</script>

<style scoped>
.expereince-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  max-width: 100%;
  width: 95%;
  margin: 0 auto;
  background-color: #ffffff;
}

.experience-card {
  margin: 10px;
  padding: 10px;
  flex-wrap: 0 0 40%;
  width: 60%;
  border-radius: 25px;
  background-color: #f9f9f9;
  border-radius: 1.7rem;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
}

.experience-card p {
  color: #525252;
}
</style>
