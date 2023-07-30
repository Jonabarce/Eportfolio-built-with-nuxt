<template>
  <div class="start-wrapper">
    <div class="picture-wrapper">
      <img src="@/assets/me.jpg" alt="" />
    </div>
    <div class="short-text-wrapper">
      <div class="title-container">
      <h1 class="animated-title">
        I'm a <span>{{ currentTitle }}</span> <br />
      </h1>
      <div>
      </div>
    </div>
      <p>
        Hi!
        <Icon
          name="openmoji:waving-hand-medium-light-skin-tone"
          color="black"
        />
        I am Jonatan Andre Vevang. I am a third year computer engineering
        student at NTNU, based in Trondheim, Norway
        <Icon name="fluent-emoji:house" />
        <Icon name="flag:bv-4x3" />
      </p>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const titles = ['student', 'team player', 'developer']
const currentTitle = ref('')
const titleIndex = ref(0)

async function typeTitle(title) {
  for (const char of title) {
    currentTitle.value += char
    await new Promise((resolve) => setTimeout(resolve, 100))
  }
}

onMounted(async () => {
  while (true) {
    await typeTitle(titles[titleIndex.value])
    await new Promise((resolve) => setTimeout(resolve, 2000))
    currentTitle.value = ''
    titleIndex.value = (titleIndex.value + 1) % titles.length
  }
})
</script>

<style scoped>
.start-wrapper {
  display: flex;
  flex-direction: row-reverse;
  align-items: center;
  justify-content: center;
  max-width: 100%;
  width: 100%;
  margin: 0 auto;
}



.short-text-wrapper {
  margin-right: 4rem;
  width: 40rem;
}

.short-text-wrapper h1 {
  font-size: 4rem;
  font-weight: 700;
  margin-bottom: 1rem;
  font-family: Mulish, sans-serif;
}

.short-text-wrapper p {
  font-size: 1.2rem;
  font-weight: 400;
  margin-bottom: 1rem;
}

.picture-wrapper img {
  -webkit-animation: morph 8s ease-in-out infinite;
  animation: morph 8s ease-in-out infinite;
  background-position: 50%;
  background-repeat: no-repeat;
  background-size: cover;
  border: 3px solid #2d2e32;
  border-radius: 60% 40% 30% 70%/60% 30% 70% 40%;
  height: 25rem;
  position: relative;
  transition: all 1s ease-in-out;
}

.animated-title span {
  color: #147efb;
}

.animated-title {
  font-family: Mulish, sans-serif;
}

@keyframes morph {
  0% {
    border-radius: 60% 40% 30% 70%/60% 30% 70% 40%;
  }
  50% {
    border-radius: 40% 60% 70% 30%/40% 70% 30% 60%;
  }
  100% {
    border-radius: 60% 40% 30% 70%/60% 30% 70% 40%;
  }
}

@media screen and (max-width: 768px) {
  .start-wrapper {
    flex-direction: column;
  }

  .short-text-wrapper {
    margin: 0 auto;
    text-align: center;
    width: 80%; /* Sett en fast bredde også for mobilvisning. Juster denne verdien etter behov */
  }

  .short-text-wrapper h1 {
    font-size: 3rem;
    font-weight: 700;
    margin-bottom: 1rem;
  }

  .short-text-wrapper p {
    font-size: 0.9rem;
    font-weight: 400;
    margin-bottom: 1rem;
  }

  .title-container h1 {
    font-size: 2.3rem;
  }
}
</style>
