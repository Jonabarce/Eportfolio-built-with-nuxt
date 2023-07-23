<template>
  <div class="socials-wrapper">
    <div>
      <h3 style="text-decoration: underline;">Socials</h3>
    </div>
    <div class="socials-icons">
      <a target="_blank" href="https://github.com/Jonabarce">
        <Icon class="the-icon" name="uil:github" />
      </a>
      <a
        target="_blank"
        href="https://www.linkedin.com/in/jonatan-andre-vevang-53120b263/"
      >
        <Icon class="the-icon" name="uil:linkedin" />
      </a>
      <a  target="_blank" href="mailto:javevang1@gmail.com">
        <Icon class="the-icon" name="ic:outline-email" />
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

.socials-icons a{
    text-decoration: none;
}

.the-icon{
width: 2.5rem;
height: 2.5rem;
}


@media screen and (max-width: 768px) {
  .socials-wrapper {
    flex-direction: column;
  }
}
</style>
