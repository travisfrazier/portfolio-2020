<template>
  <footer class="footer">
    <div class="container">
      <SocialLinks />
      <p>Copyright © Travis Frazier 2020.</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
  props: {},
  components: {
    SocialLinks: () => import('./shared/SocialLinks'),
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
.footer {
  width: 100%;
  background: #111;
  padding: 70px 0;
  display: flex;
  align-items: center;
  justify-content: center;
  p {
    color: #ffffffbd;
  }
  .social-links {
    z-index: 1;
    display: flex;
    width: 100%;
    justify-content: center;
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
    }
  }
}

//Light mode styles
.light-mode {
  .footer {
    background: $color-three;
    p {
      color: rgb(32, 32, 32);
    }
  }
}
</style>
