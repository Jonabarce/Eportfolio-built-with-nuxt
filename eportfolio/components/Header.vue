<template>
  <div class="header-wrapper">
    <NuxtLink class="header-nuxtlink" to="/">
      <div>
        <h3 style="margin-left: 1rem">Jonatan</h3>
      </div>
    </NuxtLink>
    <div class="options-wrapper">
      <div class="desktop-menu">
        <div class="header-link">
          <a @click.prevent="scrollToSection('aboutme')" href="#">
            <h2>About me</h2>
          </a>
        </div>
        <div div class="header-link">
          <a @click.prevent="scrollToSection('projects')" href="#">
            <h2>Projects</h2>
          </a>
        </div>
        <div div class="header-link">
          <a @click.prevent="scrollToSection('experience')" href="#">
            <h2>Experience</h2>
          </a>
        </div>
        <div div class="header-link">
          <a @click.prevent="scrollToSection('contact')" href="#">
            <h2>Contact me</h2>
          </a>
        </div>
      </div>
      <div
        @click="toggleMenu"
        class="mobile-menu icon"
        ref="menuIcon"
        @click.stop
      >
        <Icon name="fa:bars" />
      </div>
      <div v-if="showMenu" class="menu" ref="menu" @click.stop>
        <div class="header-link">
          <a @click.prevent="scrollToSection('aboutme')" href="#">
            <h2>About me</h2>
          </a>
        </div>
        <div div class="header-link">
          <a @click.prevent="scrollToSection('projects')" href="#">
            <h2>Projects</h2>
          </a>
        </div>
        <div div class="header-link">
          <a @click.prevent="scrollToSection('experience')" href="#">
            <h2>Experience</h2>
          </a>
        </div>
        <div div class="header-link">
          <a @click.prevent="scrollToSection('contact')" href="#">
            <h2>Contact me</h2>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { useRouter } from 'vue-router'

const router = useRouter()
let targetSection = null

router.afterEach(() => {
  if (targetSection) {
    setTimeout(() => {
      scrollToSection(targetSection)
      targetSection = null
    }, 0)
  }
})

function scrollToSection(id) {
  const element = document.getElementById(id)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}

const showMenu = ref(false)
const menu = ref(null)
const menuIcon = ref(null)

function toggleMenu() {
  showMenu.value = !showMenu.value
}

function closeMenuOnClickOutside(e) {
  if (
    menu.value &&
    !menu.value.contains(e.target) &&
    !menuIcon.value.contains(e.target)
  ) {
    closeMenu()
  }
}

function closeMenu() {
  showMenu.value = false
}

onMounted(() => {
  window.addEventListener('resize', closeMenu)
  window.addEventListener('click', closeMenuOnClickOutside)
})

onUnmounted(() => {
  window.removeEventListener('resize', closeMenu)
  window.removeEventListener('click', closeMenuOnClickOutside)
})
</script>

<style scoped>
.desktop-menu h2,
.menu a {
  white-space: nowrap;
}
.header-wrapper {
  display: flex;
  justify-content: space-between;
  position: relative;
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

.header-link a {
  text-decoration: none;
  color: #000;
  font-size: 0.8rem;
  font-weight: 700;
}

.options-wrapper {
  display: flex;
  justify-content: space-between;
  font-family: Mulish, sans-serif;
}

.desktop-menu {
  display: flex;
  justify-content: space-between;
  width: 60%;
}

.desktop-menu h2 {
  margin-right: 20px;
}

.mobile-menu {
  display: none;
  width: 40px;
  height: 40px;
  text-align: center;
  line-height: 40px;
  position: absolute;
  top: 50%;
  right: 10px;
  transform: translateY(-50%);
  cursor: pointer;
}

.icon > * {
  vertical-align: middle;
}

.menu {
  display: flex;
  flex-direction: column;
  background-color: #f1f1f1;
  position: absolute;
  right: 0;
  top: 100%;
  width: 100%;
  z-index: 1;
}

.menu a {
  text-decoration: none;
  color: #000;
  padding: 14px 16px;
  font-size: 17px;
  display: block;
}

@media screen and (max-width: 1200px) {
  .desktop-menu {
    display: none;
  }
  .mobile-menu {
    display: block;
  }
}
</style>
