<template>
  <div class="about-us-section-wrapper">
    <div class="about-us-picture">
      <div class="picture">
        <img src="@/assets/laptop.jpg" alt="" />
      </div>
    </div>
    <div class="about-us-text-section">
      <br />
      <br />
      <div class="h1-header">
        <h1 id="aboutus-h1">About me</h1>
      </div>
      <p>
        I'm a third-year student at the Norwegian University of Science and
        Technology in Trondheim, passionate about programming and tech. I thrive
        on the problem-solving aspect of coding, and there's nothing quite like
        the thrill of seeing a project come to life. <br />
        <br />

        When I'm not immersed in code, I enjoy a balanced lifestyle. I relish
        socializing with friends, staying active, and pursuing various hobbies.
        Whether it's working up a sweat at the gym, settling in for a gaming
        session, or exploring the snow-capped landscapes on my snowmobile.
      </p>
    </div>
  </div>
  <br />
  <br />
</template>

<style scoped>
.about-us-section-wrapper {
  display: flex;
  flex-direction: row-reverse;
  align-items: center;
  justify-content: space-between;
  max-width: 80%;
  width: 100%;
  margin: 0 auto;
  gap: 1rem;
}

.h1-header {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  color: #0369dd;
}

.about-us-picture {
  width: 50%;
  height: auto;
}

.about-us-text-section {
  width: 50%;
  height: auto;
  padding: 0 2rem;
  border-radius: 1rem;
  font-family: Mulish, sans-serif;
}

.about-us-text-section p {
  font-size: 20px;
  color: #525252;
  font-family: Mulish, sans-serif;
  font-size: 1.3rem;
  font-weight: 500;
  line-height: 1.5;
}

.picture {
  display: flex;
  justify-content: center;
  align-items: center;
}

.picture img {
  width: 100%;
  height: 20rem;
  border-radius: 1.7rem;
  object-fit: cover;
}

@media screen and (max-width: 1200px) {
  .about-us-text-section p {
    font-size: 18px;
  }
}

@media screen and (max-width: 900px) {
  .about-us-text-section p {
    font-size: 17px;
  }
}

@media screen and (max-width: 817px) {
  .about-us-section-wrapper {
    flex-direction: column;
    max-width: 80%;
    margin: 0 auto;
  }
  .about-us-picture {
    width: 90%;
    height: auto;
  }

  #aboutus-h1 {
    font-size: 24px;
  }

  .about-us-text-section p {
    font-size: 17px;
  }

  .about-us-text-section {
    width: 90%;
    height: auto;
    padding: 0 2rem;
  }
  .picture img {
    object-fit: contain;
  }
}

#orangeWord {
  color: orange;
}

#contact-btn {
  background-color: darkorange;
  height: 3.5rem;
  width: 18rem;
  border: none;
  transition: background-color 0.3s ease;
  border-radius: 3%;
  font-size: 1.2rem;
}

#contact-btn:hover {
  cursor: pointer;
  background-color: rgb(207, 114, 1);
}

@media only screen and (max-width: 1440px) {
  #contact-btn {
    height: 3rem;
    width: 15rem;
  }
}

@media only screen and (max-width: 1080px) {
  #contact-btn {
    height: 2.5rem;
    width: 12rem;
    font-size: 1rem;
  }
}

@media only screen and (max-width: 768px) {
  #contact-btn {
    height: 4rem;
    width: 10rem;
  }
}

@media only screen and (max-width: 600px) {
  #contact-btn {
    height: 2rem;
    width: 9rem;
  }
}

@media only screen and (max-width: 480px) {
  #contact-btn {
    height: 1.8rem;
    width: 8rem;
  }
}

@media only screen and (max-width: 390px) {
  #contact-btn {
    height: 1.6rem;
    width: 7rem;
    font-size: 0.7rem;
  }
}
</style>
