<template>
  <div class="project-section-wrapper">
    <Projects />
  </div>
</template>

<script setup>
import Projects from '@/components/Projects.vue'
</script>

<style scoped>
.project-section-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  max-width: 100%;
  width: 100%;
  margin: 0 auto;
  background-color: #f9f9f9;
}
</style>
