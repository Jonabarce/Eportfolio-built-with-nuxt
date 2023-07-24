<template>
  <div class="header-wrapper">
    <NuxtLink class="" to="/">
      <div class="header-nuxtlink">
        <div>
          <h3>Jonatan</h3>
        </div>
        <div>
          <Icon name="raphael:anonymous" />
        </div>
      </div>
    </NuxtLink>
    <div class="options-wrapper">
      <div>
        <h2>About me</h2>
      </div>
      <div>
        <h2>Projects</h2>
      </div>
      <div>
        <h2>Contact me</h2>
      </div>

      <div>
        <h2>CV</h2>
      </div>
    </div>
  </div>
</template>

<style scoped>
.header-wrapper {
  display: flex;
  justify-content: space-between;
}

.header-nuxtlink {
  display: flex;
  flex-direction: row;
  text-decoration: none;
  color: #000;
  font-size: 1.5rem;
  font-weight: 700;
  cursor: pointer;
}

.options-wrapper {
  display: flex;
  justify-content: space-between;
  width: 30%;
  font-family: Mulish, sans-serif;
}
</style>
