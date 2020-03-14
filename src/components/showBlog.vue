<template>
  <div id="show-blogs" v-theme:column="'narrow'">
    <h1>All Blog Articles</h1>
    <input type="text" v-model="search" placeholder="search blog" />
    <div v-for="blog in filteredBlogs" :key="blog.id" class="single-blog">
      <h2 v-rainbow>{{blog.title | to-uppercase}}</h2>
      <article>{{blog.body | snippet}}</article>
    </div>
  </div>
</template>
 
<script>
export default {
  data() {
    return {
      blogs: [],
      search: ""
    };
  },
  methods: {},
  computed: {
    filteredBlogs: function() {
      return this.blogs.filter(blog => {
        return blog.title.match(this.search);
      });
    }
  },
  created() {
    this.$http
      .get("https://jsonplaceholder.typicode.com/posts")
      .then(function(data) {
        this.blogs = data.body.slice(0, 10);
      });
  },
  filters: {
    "to-uppercase": function(val) {
      return val.toUpperCase();
    }
  },
  directives: {
    rainbow: {
      bind(el) {
        el.style.color =
          "#" +
          Math.random()
            .toString()
            .slice(2, 8);
      }
    }
  }
};
</script> 

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="stylus">
#show-blogs {
  max-width: 800px;
  margin: 0 auto;

  .single-blog {
    background-color: #f4f4f4;
    padding: 20px;
    margin: 20px 0;
    box-sizing: border-box;
  }
}
</style>
