<template>
  <div id="add-blog">
    <h2>add new blog content</h2>
    <form action="#">
      <label for="title">title</label>
      <input type="text" name="title" id="title" v-model.lazy="blog.title" />
      <label for="content">content</label>
      <textarea v-model.lazy="blog.content" name="content" id="content" cols="30" rows="10"></textarea>
      <div id="checkbox">
        <label for="ninjas">ninjas</label>
        <input type="checkbox" value="ninjas" v-model="blog.categories" />
        <label for="wizards">wizards</label>
        <input type="checkbox" value="wizards" v-model="blog.categories" />
        <label for="mario">mario</label>
        <input type="checkbox" value="mario" v-model="blog.categories" />
        <label for="cheese">cheese</label>
        <input type="checkbox" value="cheese" v-model="blog.categories" />
      </div>
      <select name="author" id="author" v-model="blog.author">
        <option v-for="author in authors" :key="author" :value="author">{{author}}</option>
      </select>
    </form>
    <div id="preview">
      <h3>Priview Blog</h3>
      <p>Blog title : {{blog.title}}</p>
      <p>Blog content :</p>
      <p>{{blog.content}}</p>
      <p>Blog Categories :</p>
      <ul>
        <li v-for="category in blog.categories" :key="category">{{category}}</li>
      </ul>
      <p>Blog Author : {{blog.author}}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      blog: {
        title: "",
        content: "",
        categories: [],
        author: ""
      },
      authors: ["The net ninja", "the avenger", "the vue"]
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="stylus">
$dad {
  display: block;
  width: 100%;
  padding: 8px;
}

#add-blog {
  margin: 20px auto;
  max-width: 500px;

  * {
    box-sizing: border-box;
  }
}

label {
  display: block;
  margin: 20px 0 20px;
}

input[type='text'], textarea {
  @extend $dad;
}

#preview {
  padding: 10px 20px;
  border: 1px dotted #333;
  margin: 30px 0;
}

h3 {
  margin-top: 10px;
}

#checkbox {
  input {
    display: inline block;
    margin-right: 10px;
  }

  label {
    display: inline-block;
  }
}
</style>
