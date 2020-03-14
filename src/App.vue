<template>
  <div id="app">
    <add-blog></add-blog>
  </div>
</template>

<script>
import adBlog from "@/components/adBlog.vue";

export default {
  components: {
    "add-blog": adBlog
  },
  data() {
    return {};
  },
  methods: {}
};
</script>

<style lang="stylus">
body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}
</style>
