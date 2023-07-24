<template>
  <div class="project-list">
    <h1 style="color: #0369dd">My projects</h1>
    <div class="project-card" v-for="(project, index) in projects" :key="index">
      <div class="text-content">
        <h2 style="color: #000000">{{ project.title }}</h2>
        <p>{{ project.description }}</p>
        <div class="links">
          <a class="github-href" :href="project.githubLink"
            >Source code<Icon class="the-icon" name="devicon:github"
          /></a>
          <a
            class="live-href"
            v-if="project.liveDemoLink !== 'NONE'"
            :href="project.liveDemoLink"
            >Live Demo<Icon class="the-icon" name="ph:arrow-line-up-right-thin"
          /></a>
        </div>
      </div>
      <div class="image-container">
        <img :src="`/assets/${project.image}`" :alt="project.title" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { reactive } from 'vue'
import projectData from '@/projects.json'

const projects = reactive(projectData.projects)
</script>

<style scoped>
.project-list {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.github-href,
.live-href {
  text-decoration: none;
  color: #000000;
  border-radius: 1.7rem;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.github-href:hover {
  color: #0369dd;
  cursor: pointer;
}

.live-href:hover {
  color: #0369dd;
  cursor: pointer;
}

.project-card {
  display: flex;
  flex-direction: row;
  padding: 2rem;
  margin: 2rem auto;
  width: 65%;
  height: 30%;
  justify-content: space-between;
  background-color: #fff;
  border-radius: 1.7rem;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.project-card:nth-child(odd) {
  flex-direction: row-reverse;
}

.image-container {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 65%;
}

.image-container img {
  width: 80%;
  height: 90%;
  object-fit: cover;
  border-radius: 20px;
}

.text-content {
  display: flex;
  flex-direction: column;
  width: 35%;
  height: 100%;
  font-size: 20px;
  color: #525252;
  font-family: Mulish, sans-serif;
  font-size: 1.3rem;
  font-weight: 500;
  line-height: 1.5;
}

.links {
  display: flex;
  gap: 1rem;
}

@media (max-width: 768px) {
  .project-card,
  .project-card:nth-child(odd) {
    flex-direction: column-reverse;
    align-items: center;
    width: 70%;
    height: auto;
  }
}
</style>
