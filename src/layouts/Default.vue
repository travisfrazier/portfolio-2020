<template>
  <div ref="layout" class="layout light-mode">
    <Header v-on:toggleMode="updateMode" />
    <slot />
  </div>
</template>

<script>
import Header from '~/components/Header.vue';
//import Footer from '~/components/Footer.vue'

export default {
  components: {
    Header
  },
  methods: {
    updateMode() {
      console.log('triggered');
      this.$refs.layout.classList.toggle('light-mode');
    }
  }
};
</script>

