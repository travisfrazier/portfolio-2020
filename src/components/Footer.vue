<template>
  <footer class="footer">
    <div class="container">
      <social-links />
      <p>Copyright © Travis Frazier 2022.</p>
    </div>
  </footer>
</template>


<script>
import SocialLinks from './SocialLinks.vue';
export default {
  components: { SocialLinks },
  name: "Footer",
  props: {},
  methods: {}
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
      border: 1px solid #3e50b4;
      margin: 0 0.5rem;
    }
    i {
      display: table-cell;
      vertical-align: middle;
      color: #3e50b4;
    }
  }
}
</style>
