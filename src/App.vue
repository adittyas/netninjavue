<template>
  <div id="app">
    <router-link to="/">Home</router-link>|
    <router-link to="/add">Add Post</router-link>|
    <router-link to="/show">Show Post</router-link>|
    <router-view></router-view>
    <!-- <show-blog></show-blog>
    <list-blog></list-blog>
    <add-blog v-show="t"></add-blog>-->
  </div>
</template>

<script>
// import adBlog from "@/components/adBlog.vue";
// import showBlog from "@/components/showBlog.vue";
// import listBlog from "@/components/listBlog.vue";

export default {
  components: {
    // "add-blog": adBlog,
    // "show-blog": showBlog,
    // "list-blog": listBlog
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
