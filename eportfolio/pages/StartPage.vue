<template>
  <div class="start-section-wrapper">
    <Start />
    <TechStack />
    <Socials />
  </div>
</template>

<script setup>
import Start from '@/components/Start.vue'
import TechStack from '@/components/TechStack.vue'
import Socials from '@/components/Socials.vue'
</script>

<style scoped>
.start-section-wrapper {
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
