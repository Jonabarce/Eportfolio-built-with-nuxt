<template>
<div class="website-wrapper">
<StartPage />
<AboutMePage />
<ProjectPage />
<ContactPage />
</div>
</template>


<script setup>


import AboutMePage from '@/pages/AboutMePage.vue'
import ContactPage from '@/pages/ContactPage.vue'
import ProjectPage from '@/pages/ProjectPage.vue';
import StartPage from '@/pages/StartPage.vue';


</script>


<style scoped>
.website-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  max-width: 100%;
  width: 100%;
  margin: 0 auto;
}
</style>