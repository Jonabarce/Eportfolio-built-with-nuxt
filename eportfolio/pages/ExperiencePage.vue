<template>
  <div class="experience-wrapper">
    <Experience />
  </div>
</template>

<script setup>
import Experience from '@/components/Experience.vue'
</script>

<style scoped>
.experience-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  max-width: 100%;
  width: 100%;
  margin: 0 auto;
  background-color: #ffffff;
}
</style>
