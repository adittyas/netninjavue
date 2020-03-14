<template>
  <div id="app">
    <show-blog></show-blog>
    <add-blog v-show="t"></add-blog>
  </div>
</template>

<script>
import adBlog from "@/components/adBlog.vue";
import showBlog from "@/components/showBlog.vue";

export default {
  components: {
    "add-blog": adBlog,
    "show-blog": showBlog
  },
  data() {
    return {
      t: false
    };
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
