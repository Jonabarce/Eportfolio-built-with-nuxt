<template>
  <div class="techstack-wrapper">
    <div>
      <h3 style="text-decoration: underline;">TechStack</h3>
    </div>
    <div>
      <Icon class="skill-icon" name="skill-icons:java-dark" />
      <Icon class="skill-icon" name="skill-icons:python-dark" />
      <Icon class="skill-icon" name="skill-icons:html" />
      <Icon class="skill-icon" name="skill-icons:css" />
      <Icon class="skill-icon" name="skill-icons:javascript" />
      <Icon class="skill-icon" name="skill-icons:nuxtjs-dark" />
      <Icon class="skill-icon" name="skill-icons:vuejs-dark" />
      <Icon class="skill-icon" name="skill-icons:react-dark" />
      <Icon class="skill-icon" name="skill-icons:mysql-dark" />
      <Icon class="skill-icon" name="skill-icons:spring-dark" />
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

.skill-icon{
  width: 2.5rem;
  height: 2.5rem;
}

@media screen and (max-width: 768px) {
  .techstack-wrapper {
    flex-direction: column;
  }
}
</style>
