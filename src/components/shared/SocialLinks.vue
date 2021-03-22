<template>
  <div class="social-links">
    <a href="https://github.com/travisfrazier">
      <i><font-awesome :icon="['fab', 'github']"/></i>
    </a>
    <a href="https://www.instagram.com/travfrazier/">
      <i><font-awesome :icon="['fab', 'instagram']"/></i>
    </a>
    <a href="https://www.twitter.com/traviscoding">
      <i><font-awesome :icon="['fab', 'twitter']"/></i>
    </a>
    <a href="https://www.linkedin.com/in/traviscoding/">
      <i><font-awesome :icon="['fab', 'linkedin']"/></i>
    </a>
  </div>
</template>

<script>
export default {
  name: 'SocialLinks',
  props: {},
  methods: {},
};
</script>

<style lang="scss" scoped>
.social-links {
  z-index: 1;
  display: flex;
  width: 100%;
  max-width: 100%;
  justify-content: center;
  @media only screen and (max-width: 812px) and (min-width: 376px) {
    margin-top: 0.25rem;
  }
  a {
    display: inline-table;
    text-align: center;
    height: 35px;
    width: 35px;
    color: #fff;
    border-radius: 50%;
    border: 1px solid $color-links;
    margin: 0 0.5rem;
  }
  i {
    display: table-cell;
    vertical-align: middle;
    color: $color-links;
    text-shadow: 2px 2px 10px $color-black;
  }
}
</style>
