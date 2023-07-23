<template>
    <div class="aboutMe-section-wrapper">
        <AboutMe />
    </div>
</template>



<script setup>

import AboutMe from '@/components/AboutMe.vue'


</script>


<style scoped>
.aboutMe-section-wrapper {
    display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  max-width: 100%;
  width: 100%;
  margin: 0 auto;
}
</style>
