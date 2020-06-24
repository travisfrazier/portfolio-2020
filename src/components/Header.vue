<template>
  <header class="header section">
    <figure class="mobile-menu">
      <img
        v-on:click="toggleMenu"
        class="button"
        src="../assets/images/menu.png"
      />
    </figure>
    <nav class="desktop-nav">
      <toggle-button
        color="#82C7EB"
        @change="onChangeEventHandler"
        :labels="{ checked: 'Light Mode', unchecked: 'Dark Mode' }"
        :width="100"
        :height="30"
      />
      <ul>
        <li>
          <a href="#home">Home</a>
        </li>
        <li>
          <a href="#about">About</a>
        </li>
        <li>
          <a href="#projects">Projects</a>
        </li>
        <li>
          <a href="#contact">Contact</a>
        </li>
        <li>
          <a href="https://represent.io/travisfrazier" target="_blank">
            Resumé
          </a>
        </li>
      </ul>
    </nav>
    <nav v-show="showMenu" class="mobile-nav">
      <ul>
        <li>
          <a href="#home">Home</a>
        </li>
        <li>
          <a href="#about">About</a>
        </li>
        <li>
          <a href="#projects">Projects</a>
        </li>
        <li>
          <a href="#contact">Contact</a>
        </li>
        <li>
          <a href="https://represent.io/travisfrazier" target="_blank">
            Resumé
          </a>
        </li>
      </ul>
    </nav>
    <div class="layer" />
    <p>
      Hello, My name is <strong class="name">Travis Frazier</strong> and I'm a
    </p>
    <div class="typewriter">
      <h1>
        FRONT-END DEVELOPER
      </h1>
    </div>
    <p>creating modern and responsive web experiences.</p>
    <SocialLinks />
    <a class="arrow-container">
      <i class="fa fa-angle-double-down arrow" />
    </a>
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: {},
  data() {
    return {
      showMenu: false,
      lightMode: false,
    };
  },
  components: {
    SocialLinks: () => import('./shared/SocialLinks'),
  },
  methods: {
    toggleMenu() {
      console.log('hey');
      this.showMenu = !this.showMenu;
    },
    onChangeEventHandler() {
      this.$emit('toggleMode');
    },
  },
};
</script>

<style lang="scss" scoped>
.typewriter {
  z-index: 1;
}

.typewriter h1 {
  overflow: hidden;
  border-right: 0.15em solid orange;
  white-space: nowrap;
  margin: 0 auto;
  letter-spacing: 0.25rem;
  animation: typing 3.5s steps(40, end), blink-caret 0.75s step-end infinite;
}

/* The typing effect */
@keyframes typing {
  from {
    width: 0;
  }
  to {
    width: 100%;
  }
}

/* The typewriter cursor effect */
@keyframes blink-caret {
  from,
  to {
    border-color: transparent;
  }
  50% {
    border-color: orange;
  }
}

header {
  background-image: url('../assets/images/laptop.jpg');
  background-size: cover;
  background-position: center;
  height: 100vh;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  nav {
    position: absolute;
    top: 0rem;
    width: 100%;
    display: flex;
    justify-content: space-between;
    z-index: 999;
    align-items: center;
    max-width: 95%;
    @media only screen and (max-width: 768px) {
      justify-content: center;
      background-color: transparent;
      padding-top: 1.25rem;
      background-color: #212121;
    }
    ul {
      list-style-type: none;
      width: 25rem;
      z-index: 3;
      display: flex;
      justify-content: space-between;
      @media only screen and (max-width: 768px) {
        flex-direction: column;
        //justify-content: flex-start;
        align-items: flex-start;
        margin-top: 2.5rem;
      }
      li {
        @media only screen and (max-width: 768px) {
          padding: 0.5rem;
          font-size: 1.15rem;
          width: 100%;
        }
        a {
          color: #f5f5f5;
          @media only screen and (max-width: 768px) {
            padding-right: 90%;
          }
          &:visited {
            color: #f5f5f5;
          }
          &:hover {
            color: #ff3f80;
            //border-bottom: 1px solid #118aaf;
          }
        }
      }
    }
  }
  //Desktop Nav
  .desktop-nav {
    @media only screen and (max-width: 768px) {
      display: none;
    }
  }
  //Mobile Nav
  .mobile-menu {
    position: absolute;
    top: 1rem;
    z-index: 1000;
    display: none;
    margin: auto;
    @media only screen and (max-width: 768px) {
      display: block;
    }
    img {
      width: 2rem;
      height: 2rem;
    }
  }

  //Toggle menu
  .block {
    display: flex !important;
  }
  //end
  .layer {
    background-color: #000000ab;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }
  h1 {
    z-index: 1;
    font-weight: 400;
    width: 100%;
    text-align: center;
    color: #f5f5f5;
    font-size: 5vw;
    margin: 0.25rem 0rem;
    padding-top: 0rem;
    @media only screen and (max-width: 812px) {
      //font-size: 2.4rem;
      font-size: 6vw;
      //width: 95%;
    }
  }
  p {
    z-index: 1;
    font-size: 1.75vw;
    color: #f5f5f5;
    @media only screen and (max-width: 812px) and (min-width: 415px) {
      margin: 0.25rem;
    }
    @media only screen and (max-width: 600px) {
      font-size: 1rem;
      text-align: center;
      //width: 95%;
    }
  }
  .arrow-container {
    display: flex;
    justify-content: center;
  }
  .arrow {
    color: #ffffffcb;
    //width: 3rem;
    z-index: 3;
    position: absolute;
    bottom: 2rem;
    font-size: 2rem;
    @media only screen and (max-width: 767px) and (min-width: 415px) {
      bottom: 0.75rem;
    }
  }
}

//Light Mode
.light-mode {
  h1,
  p {
    color: rgb(32, 32, 32);
  }
  header {
    background-image: url('../assets/images/light-mode.jpg');
  }
  .layer {
    background-color: #ffffff7a;
  }
  ul {
    a {
      color: rgb(32, 32, 32);
      &:visited {
        color: rgb(32, 32, 32);
      }
      &:hover {
        color: rgb(32, 32, 32);
      }
    }
  }
}
</style>
