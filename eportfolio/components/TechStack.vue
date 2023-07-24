<template>
  <div class="techstack-wrapper">
    <div>
      <h3 class="techstack-title">TechStack</h3>
    </div>
    <div class="icon-wrapper">
      <Icon class="skill-icon" name="skill-icons:java-light" />
      <Icon class="skill-icon" name="skill-icons:python-light" />
      <Icon class="skill-icon" name="skill-icons:html" />
      <Icon class="skill-icon" name="skill-icons:css" />
      <Icon class="skill-icon" name="skill-icons:javascript" />
      <Icon class="skill-icon" name="skill-icons:nuxtjs-light" />
      <Icon class="skill-icon" name="skill-icons:vuejs-light" />
      <Icon class="skill-icon" name="skill-icons:react-light" />
      <Icon class="skill-icon" name="skill-icons:mysql-light" />
      <Icon class="skill-icon" name="skill-icons:spring-light" />
    </div>
  </div>
</template>

<style scoped>
.techstack-wrapper {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  max-width: 100%;
  width: 100%;
  margin: 0 auto;
}

.techstack-title {
  font-size: 24px;
  margin-right: 1rem;
  font-family: Mulish, sans-serif;
}

.icon-wrapper {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  justify-content: center;
}

.skill-icon {
  width: 3.5rem;
  height: 3.5rem;
  border-radius: 50%;
}

@media screen and (max-width: 768px) {
  .techstack-wrapper {
    flex-direction: column;
  }

  .techstack-title {
    margin-bottom: 1rem;
  }
}
</style>
