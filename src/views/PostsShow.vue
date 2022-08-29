<script>
import axios from 'axios';

  export default {
    data: function () {
      return {
        message: "Welcome to Vue Show!.js!",
        post: {}
      };
    },
    created: function () {
      this.PostShow();
    },
    methods: {
      PostShow: function () {
        console.log('show post..');
        console.log(this.$route.params.id);
        axios.get("/posts/" + this.$route.params.id + ".json").then(response => {
          console.log(response.data);
          this.post = response.data;
        })
      }
    },
  };
</script>

<template>
  <div class="posts-show">
    <h3>{{ post.title }}</h3>
    <p>{{ post.body }}</p>
    <p>{{ post.image }}</p>
 </div>
</template>

<style></style>