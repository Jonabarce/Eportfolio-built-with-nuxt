<template>
  <div class="start-wrapper">
    <div class="picture-wrapper">
      <img src="@/assets/me.jpg" alt="" />
    </div>
    <div class="short-text-wrapper">
      <h1>
        Computer engineering student
        <Icon name="ph:computer-tower-fill" color="purple" />
      </h1>
      <p>
        Hi!
        <Icon
          name="openmoji:waving-hand-medium-light-skin-tone"
          color="black"
        />
        I am Jonatan Andre Vevang. I am a third year computer engineering
        student
      </p>
      <p>at NTNU, based in Trondheim, Norway</p>
    </div>
  </div>
</template>

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
}
</style>
