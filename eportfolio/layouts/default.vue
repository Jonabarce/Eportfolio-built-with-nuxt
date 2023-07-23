<template>
  <div class="layout-container">
    <Header />
    <div class="content-container">
      <slot />
    </div>
    <Footer />
  </div>
</template>

<script setup>
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'
</script>

<style scoped>
.layout-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.content-container {
  flex-grow: 1;
  width: 100%;
  display: flex;
  justify-content: center;
}
</style>
