<template>
  <section id="projects" class="projects section">
    <div class="section-container">
      <div class="section-heading section-container">
        <h2>My Latest Projects</h2>
        <p>
          The projects below are to demonstarate my competancy in HTML,
          CSS/SASS, Vanilla JavaScript, and the front-end framework Vue.js. I've
          worked on many large builds and websites but most companies have rules
          against displaying projects so I want to be respectful. For more
          examples or links please reach out to me directly.
        </p>
      </div>
      <div class="project-toggles">
        <button @click="toggleProject">Vanilla JS</button>
        <button @click="toggleProject">Vue.js</button>
        <button @click="toggleProject">Other</button>
        <button @click="toggleProject">All</button>
      </div>
      <div class="projects_container">
        <div
          v-if="all || vue"
          data-aos="fade-right"
          class="project project-two"
        >
          <a href="https://space-tourism-vuejs.netlify.app" target="_blank">
            <img src="../assets/images/projects/space-tourism.png" />
            <div class="project-inner">
              <div class="project-info">
                <h3>Space Tourism Vue Site</h3>
                <p>
                  Developed interactive Vue.js static site with Gridsome.js, all
                  custom styles based on Figma design
                </p>
                <span>View Site</span>
              </div>
            </div>
          </a>
        </div>
        <div v-if="all || vanilla" class="project project-two">
          <a href="https://travisfrazier.github.io/matchgame/" target="_blank">
            <img src="../assets/images/projects/guess.png" />
            <div class="project-inner">
              <div class="project-info">
                <h3>Vanilla JS Match Game</h3>
                <p>
                  Developed this match game application. Built with: Vanilla
                  JavaScript, Bootstrap 4, and custom CSS.
                </p>
                <span>View Site</span>
              </div>
            </div>
          </a>
        </div>
        <div v-if="all || vue" class="project project-two">
          <a href="https://vuejs-todo-application.netlify.app/" target="_blank">
            <img src="../assets/images/projects/todo-vue.png" />
            <div class="project-inner">
              <div class="project-info">
                <h3>Over Engineered Vue To Do App</h3>
                <p>
                  Simple and clean app built with Vue.js. Includes a dark mode,
                  drag and drop, and more. Built based on Figma design.
                </p>
                <span>View Site</span>
              </div>
            </div>
          </a>
        </div>
        <div v-if="all || other" class="project project-two">
          <a href="https://miserable-media.netlify.app/" target="_blank">
            <img src="../assets/images/projects/miserable-media.png" />
            <div class="project-inner">
              <div class="project-info">
                <h3>Miserable Media</h3>
                <p>Custom built basic website with headless CMS.</p>
                <span>View Site</span>
              </div>
            </div>
          </a>
        </div>
        <div v-if="all || other" class="project project-two">
          <a href="https://themimosasnailbar.com" target="_blank">
            <img src="../assets/images/projects/mimosas-new.png" />
            <div class="project-inner">
              <div class="project-info">
                <h3>Mimosas Nail Bar</h3>
                <p>
                  Developed client website following design spec. Incorporates a
                  Headless CMS for content updates. Built with: SASS, HTML5,
                  Vanilla JavaScript, VueJS, and Jekyll.
                </p>
                <span>View Site</span>
              </div>
            </div>
          </a>
        </div>
        <div v-if="all || vue" class="project project-two">
          <a href="https://vue-movie-list.netlify.app/" target="_blank">
            <img src="../assets/images/projects/movie-app.png" />
            <div class="project-inner">
              <div class="project-info">
                <h3>Nuxt (Vue) Movie List</h3>
                <p>Single page demo app built with Vue / NuxtJS.</p>
                <span>View Site</span>
              </div>
            </div>
          </a>
        </div>
        <div v-if="all || vue" class="project project-two">
          <a
            href="https://travisfrazier.github.io/vue-drum-pad/"
            target="_blank"
          >
            <img src="../assets/images/projects/mpc-kit.png" />
            <div class="project-inner">
              <div class="project-info">
                <h3>Vue.js Drum Pad</h3>
                <p>
                  Designed and Developed a single page drum pad application.
                  Built with: Vue.js CDN, SASS, and HTML5.
                </p>
                <span>View Site</span>
              </div>
            </div>
          </a>
        </div>
        <div v-if="all || vanilla" class="project project-two">
          <a
            href="https://codepen.io/travisfrazier/full/bKyzep/"
            target="_blank"
          >
            <img src="../assets/images/projects/weather.png" />
            <div class="project-inner">
              <div class="project-info">
                <h3>Vanilla JS Weather App</h3>
                <p>
                  Designed and Developed a single page weather app. Built with:
                  Vanilla JavaScript, Fetch API, and SASS.
                </p>
                <span>View Site</span>
              </div>
            </div>
          </a>
        </div>
        <div v-if="all || vue" class="project project-two">
          <a href="https://data-intake-vue.netlify.app/" target="_blank">
            <img src="../assets/images/projects/data-intake.jpg" />
            <div class="project-inner">
              <div class="project-info">
                <h3>Data Intake Wizard</h3>
                <p>
                  Designed and Developed a single page app for collecting data.
                  Built with: Vue and Vue Formulate. The image upload creates a
                  Base64 string and then submits all the data to a server via Axios.
                </p>
                <span>View Site</span>
              </div>
            </div>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Project",
  data() {
    return {
      vanilla: false,
      vue: false,
      shopify: false,
      squarespace: false,
      other: false,
      all: true,
    };
  },
  methods: {
    toggleProject(event) {
      if (event.target.textContent === "Vanilla JS") {
        this.vanilla = true;
        this.vue = false;
        this.other = false;
        this.all = false;
      } else if (event.target.textContent === "Vue.js") {
        this.vanilla = false;
        this.vue = true;
        this.other = false;
        this.all = false;
      } else if (event.target.textContent === "Other") {
        this.vanilla = false;
        this.vue = false;
        this.other = true;
        this.all = false;
      } else if (event.target.textContent === "All") {
        this.vanilla = false;
        this.vue = false;
        this.other = false;
        this.all = true;
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.project-toggles {
  display: flex;
  justify-content: center;
  gap: 30px;
  margin-bottom: 50px;
  flex-wrap: wrap;
  padding: 0 15px;
}
.projects {
  background-color: #212121;
  padding-bottom: 3rem;
}

a {
  color: black;
  overflow: hidden;
  &:visited {
    color: black;
  }
}

.project-inner {
  position: absolute;
  display: flex;
  justify-content: center;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  height: 100%;
  width: 100.1%;
  opacity: 0;
  transition: 0.5s ease;
  background-color: #3e50b4e1;
}

.project {
  width: 100%;
  position: relative;
  overflow: hidden;
  img {
    width: 100%;
    opacity: 1;
    transition: 0.5s ease;
    backface-visibility: hidden;
    object-fit: cover;
    height: 315px;
  }
  .project-info {
    position: absolute;
    text-align: center;
    top: 25%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    h3 {
      margin: 0 auto;
      color: white;
    }
    p {
      color: #ffffffce;
      width: 90%;
      margin-right: auto;
      margin-left: auto;
      font-weight: 500;
      line-height: 1.5;
    }
    span {
      color: #ffffff;
    }
  }
}

.project:hover img {
  opacity: 0.3s;
  transform: scale(1.04);
}

.project:hover .project-inner {
  opacity: 1;
}

.projects_container {
  overflow: scroll;
  display: grid;
  padding-bottom: 3rem;
  grid-template-columns: repeat(auto-fit, minmax(25%, 1fr));
  @media only screen and (max-width: 1100px) {
    grid-template-columns: repeat(auto-fit, minmax(325px, 1fr));
  }
  grid-gap: 1rem;
}

.section-heading {
  display: flex;
  flex-direction: column;
  font-size: 1.25rem;
  color: rgba(255, 255, 255, 0.7333333333);
  text-align: center;
  align-items: center;
  p {
    max-width: 80%;
  }
}

h2 {
  margin-bottom: 0rem;
}
</style>