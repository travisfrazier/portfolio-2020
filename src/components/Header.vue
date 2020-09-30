<template>
  <header class="header section">
    <div class="mobile-menu-container">
      <!-- <toggle-button
        color="#82C7EB"
        @change="onChangeEventHandler"
        :labels="{ checked: 'Light Mode', unchecked: 'Dark Mode' }"
        :width="100"
        :height="30"
      /> -->
      <Button class="mode-toggle-button" v-bind:class="{ activeDark: isActive }" @click="onChangeEventHandler">{{
        buttonText ? 'Light Mode' : 'Dark Mode'
      }}</Button>
      <div v-on:click="toggleMenu" class="mobile-menu">
        <div class="bar1"></div>
        <div class="bar2"></div>
        <div class="bar3"></div>
      </div>
    </div>
    <nav class="desktop-nav">
      <Button class="mode-toggle-button" v-bind:class="{ activeDark: isActive }" @click="onChangeEventHandler">{{
        buttonText ? 'Light Mode' : 'Dark Mode'
      }}</Button>
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
      buttonText: false,
      isActive: false
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
      this.buttonText = !this.buttonText;
      this.isActive = !this.isActive;
    },
  },
};
</script>

<style lang="scss" scoped>
.mode-toggle-button {
  width: 7.25rem;
  height: 2rem;
  border: none;
  border-radius: 5px;
  background-color: #000;
  color: $color-one;
  cursor: pointer;
  font-family: $font-secondary;
  padding-top: .1rem;
  &:hover {
    color: $color-white;
  }
}
.activeDark {
  background-color: #fff !important;
  &:hover {
    color: $color-black;
  }
}
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
            color: $color-one;
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
  .vue-js-switch {
    z-index: 999;
  }
  //Mobile Nav
  .mobile-nav {
    max-width: 100%;
    display: flex;
    justify-content: flex-start;
    ul {
      padding: 0;
      width: 95%;
      margin-left: auto;
      margin-right: auto;
    }
  }
  .mobile-menu-container {
    z-index: 1000;
    display: none !important;
    width: 90% !important;
    position: absolute;
    top: 1rem;
    display: flex;
    justify-content: space-between;
    width: 100%;
    align-items: center;
    @media only screen and (max-width: 768px) {
      display: flex !important;
    }
  }
  figure {
    margin: 0;
  }
  .mobile-menu {
    z-index: 1000;
    display: none;
    @media only screen and (max-width: 768px) {
      display: block;
    }
    img {
      width: 2rem;
      height: 2rem;
    }
    .bar1,
    .bar2,
    .bar3 {
      width: 35px;
      height: 5px;
      background-color: #fff;
      margin: 6px 0;
      transition: 0.4s;
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
      color: $color-black;
      &:visited {
        color: $color-black;
      }
      &:hover {
        color: $color-one;
      }
    }
  }
  nav {
    @media only screen and (max-width: 768px) {
      background-color: $color-three;
    }
  }
  .bar1,
  .bar2,
  .bar3 {
    background-color: $color-black !important;
  }
}
</style>
