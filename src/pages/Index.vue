<template>
  <Layout>
    <About />
    <Projects :projects="$page.projects.edges" />
    <Contact />
  </Layout>
</template>

<page-query>
query Posts {
	projects: allProjectPost {
    edges {
      node {
        id
        image
        title
        desc
        url
        button
        path
      }
    }
  }
}
</page-query>

<script>
import About from '~/components/About.vue';
import Projects from '~/components/Projects.vue';
import Contact from '~/components/Contact.vue';

export default {
  metaInfo: {
    title: `Travis Frazier`,
  },
  components: {
    About,
    Projects,
    Contact,
  },
};
</script>

<style></style>
