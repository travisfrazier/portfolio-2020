<template>
  <section class="about-me section" id="about">
    <div class="about-me-content">
      <div class="section-heading">
        <h2>About Me</h2>
      </div>
      <div class="about-content">
        <img class="profile-img" src="../assets/images/me.jpg" />
        <div class="about-description">
          <p>
            I am <ins>Travis Frazier</ins>. Front-end Developer. Musician.
            Traveler. Hardcore adventurer. Devoted husband. Freediver.
          </p>
          <p>
            I am passionate about creating user interfaces for web and mobile.
            I've worked with a variety of companies both big and small. I love helping 
            my clients and team achieve their web goals by creating a well built online presense.
          </p>
          <p>
            Continual education and being relevant on new trends are both very
            important to me and currently I'm focusing on Vue.JS. It's not
            uncommon to find me coding through the weekends or on the road.
            Check out my latest projects below or view more on my
            <u>
              <a href="https://github.com/travisfrazier" target="_blank">
                GitHub.
              </a></u
            >I am eager to apply my experience and skills to better your
            company or project!
          </p>
          <a href="#contact">
            <button>Contact Me</button>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>



<script>
export default {
  name: 'About'
};
</script>

<style lang="scss" scoped>
.about-me {
  padding-bottom: 2rem;
  background: #424242;
  .about-me-content {
    max-width: 1400px;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }
  .about-content {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-gap: 4rem;
    align-items: center;
    padding-bottom: 3rem;
    width: 90%;
    @media only screen and (max-width: 768px) {
      grid-template-columns: 1fr;
      grid-gap: 1rem;
      align-items: center;
      justify-items: center;
    }
  }
}
.about-description {
  p {
    font-size: 1.25rem;
    color: #ffffffbb;
  }
}
.profile-img {
  width: 100%;
  border-radius: 15px;
  object-fit: cover;
  max-height: 525px;
}
</style>