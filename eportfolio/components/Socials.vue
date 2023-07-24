<template>
  <div class="socials-wrapper">
    <div>
      <h3 class="socials-title">Socials</h3>
    </div>
    <div class="socials-icons">
      <a target="_blank" href="https://github.com/Jonabarce">
        <Icon class="the-icon" name="devicon:github" />
      </a>
      <a
        target="_blank"
        href="https://www.linkedin.com/in/jonatan-andre-vevang-53120b263/"
      >
        <Icon class="the-icon" name="devicon:linkedin" />
      </a>
      <a target="_blank" href="mailto:javevang1@gmail.com">
        <Icon class="the-icon" name="fluent-emoji:e-mail" />
      </a>
    </div>
  </div>
</template>

<style scoped>
.socials-wrapper {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  max-width: 100%;
  width: 100%;
  margin: 0 auto;
}

.socials-title {
  font-size: 24px;
  margin-right: 1rem;
  font-family: Mulish, sans-serif;
}

.socials-icons {
  display: flex;
  gap: 10px;
}

.socials-icons a {
  text-decoration: none;
}

.the-icon {
  width: 3.5rem;
  height: 3.5rem;
}

@media screen and (max-width: 768px) {
  .socials-wrapper {
    flex-direction: column;
  }

  .socials-title {
    margin-bottom: 1rem;
  }
}
</style>
