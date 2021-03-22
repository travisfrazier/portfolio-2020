<template>
  <section id="projects" class="projects section">
    <div class="section-heading">
      <h2>Latest Projects</h2>
    </div>
    <div class="projects_container">
      <div 
        class="project project-two"
        v-for="item in projects"
        :key="item.node.id"
      >
        <a :href="item.node.url" target="_blank">
          <g-image :src="item.node.image" :alt="item.node.title" />
          <div class="project-inner">
            <div class="project-info">
              <h3>{{ item.node.title }}</h3>
              <p>
                {{ item.node.desc }}
              </p>
              <span>{{ item.node.button }}</span>
            </div>
          </div>
        </a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    projects: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
.projects {
  background-color: #212121;
  padding-bottom: 3rem;
}

a {
  color: $color-black;
  overflow: hidden;
  &:visited {
    color: $color-black;
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
  }
  .project-info {
    //position: absolute;
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
      width: 85%;
      margin-right: auto;
      margin-left: auto;
      font-weight: 500;
      line-height: 1.5;
    }
    span {
      color: $color-white;
    }
  }
}

.project-disclaimer {
  width: 90%;
  margin-top: -1rem;
  text-align: center;
  margin-right: auto;
  margin-left: auto;
  color: #ffffff8e;
}

.project:hover img {
  opacity: 0.3s;
  transform: scale(1.04);
}

.project:hover .project-inner {
  opacity: 1;
}

.projects_container {
  display: grid;
  padding-left: 1rem;
  padding-right: 1rem;
  padding-bottom: 3rem;
  grid-template-columns: 1fr 1fr;
  @media only screen and (max-width: 767px) {
    grid-template-columns: 1fr;
  }
  grid-gap: 1rem;
}
//Light Mode Styles
.light-mode {
  .projects {
    background-color: $color-three;
  }
  .section-heading {
    h2 {
      color: rgb(32, 32, 32);
    }
  }
}
</style>
