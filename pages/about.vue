<template>
  <div class="about">
    <h2>About The Smiling Onion</h2>
    <div v-html="page.content.rendered"></div>
  </div>
</template>

<script>
import pagesIndex from "./wpPages.js"
export default {
  name: "AboutPage",
  created() {
    this.$store.dispatch("getPage", "about")
  },
  computed: {
    page() {
      return this.$store.state.pages[pagesIndex["about"]]
    },
  },
}
</script>

<style lang="scss" scoped>
.about {
  margin: 30px auto 50px;
  max-width: 800px;
  padding: 50px 50px 70px;
  background: white;
}

p {
  margin: 15px 0 20px;
}
</style>
