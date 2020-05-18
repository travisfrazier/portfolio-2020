<template>
  <section class="about-me section" id="about">
    <div class="about-me-content">
      <div class="section-heading">
        <h2>{{ settings.section_title }}</h2>
      </div>
      <div class="about-content">
        <img class="profile-img" :src="`${settings.profile_image}`" />
        <div class="about-description" v-html="`${settings.bio}`">
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
  name: 'About',
  data() {
    return {
      settings: require("../../data/about.json")
    }
  },
  props: {
    title: String
  }
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
  button {
    width: 11rem;
    height: 3.25rem;
    border: none;
    border-radius: 5px;
    background-color: #ff3f80;
    color: white;
    font-size: 1.25rem;
  }
}

.about-description {
  color: #ffffff;
  font-size: 1.25rem;
}

.profile-img {
  width: 100%;
  border-radius: 15px;
}
</style>
