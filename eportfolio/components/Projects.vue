<template>
  <div class="project-list">
    <h1 style="color: #0369dd">My projects</h1>
    <div class="project-card" v-for="(project, index) in projects" :key="index">
      <div class="text-content">
        <h3 style="color: #000000">{{ project.title }}</h3>
        <p id="description">{{ project.description }}</p>
        <div class="links">
          <a
            class="github-href"
            v-if="project.githubLink !== 'NONE'"
            :href="project.githubLink"
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
        <img :src="`${project.image}`" :alt="project.title" />
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

.text-contenct h3 {
  font-size: 16px;
}

#description {
  font-size: 16px;
}

.github-href,
.live-href {
  text-decoration: none;
  color: #000000;
  border-radius: 1.7rem;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
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
  width: 950px;
  height: 490px;
  justify-content: space-between;
  background-color: #fff;
  border-radius: 1.7rem;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
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
  width: 482px;
  height: 307px;
  object-fit: cover;
  display: block;
  border-radius: 1.7rem;
}

.text-content {
  display: flex;
  flex-direction: column;
  width: 35%;
  height: 100%;
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

@media (max-width: 1299px) {
  .project-card,
  .project-card:nth-child(odd) {
    flex-direction: column-reverse;
    align-items: center;
    width: 60%;
    height: auto;
  }
  .image-container img {
    width: 530px;
    height: 307px;
    object-fit: cover;
    display: block;
    border-radius: 1.7rem;
  }
  .text-content {
    width: 60%;
  }
}

@media (max-width: 1130px) {
  .image-container img {
    width: 490px;
    height: 340px;
  }
  .text-content {
    width: 70%;
  }
}

@media (max-width: 1000px) {
  .project-card,
  .project-card:nth-child(odd) {
    width: 570px;
    height: 750px;
  }

  .image-container img {
    width: 560px;
    height: 300px;
    object-fit: cover;
    display: block;
    border-radius: 1.7rem;
  }

  .text-content {
    width: 70%;
  }
}



  @media (max-width: 660px) {
    .project-card,
    .project-card:nth-child(odd) {
      width: 400px;
      height: 1000px;
    }
    .image-container img {
      width: 400px;
      height: 200px;
      object-fit: cover;
      display: block;
      border-radius: 1.7rem;
    }

    .links {
      flex-direction: column;
    }
  }

  @media (max-width: 500px) {
    .project-card,
    .project-card:nth-child(odd) {
      width: 250px;
      height: 1000px;
    }
    .image-container img {
      width: 400px;
      height: 200px;
      object-fit: cover;
      display: block;
      border-radius: 1.7rem;
    }

    .links {
      flex-direction: column;
    }
  }

</style>
