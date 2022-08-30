<script>
import axios from 'axios';

  export default {
    data: function () {
      return {
        message: "Welcome to Vue.js!!!!!!",
        posts: []
      };
    },
    created: function () {
      this.postsIndex();
    },
    methods: {
      postsIndex: function() {
        console.log('getting posts index...');
        axios.get("/posts.json").then(response => {
          console.log(response.data);
          this.posts = response.data;
        })
      }
    },
  };
</script>

<template>
  <div class="posts-index">
    <h1>{{ message }}</h1>
    <!-- {{ posts }} -->
    <div v-for="post in posts">
    
    <p>{{ post.user_id }}</p>
    <!-- <p> <a v-bind:href="'posts/' + post.id"> {{ post.title }}</a></p> -->
     <p> <a v-bind:href="`/posts/${post.id}`"> {{ post.title }}</a></p>
    <p>{{ post.body }}</p>
    <p>{{ post.image }}</p>
    <p>{{ post.id }}</p>
    </div>
    <hr/>
  </div>
</template>
<style></style>