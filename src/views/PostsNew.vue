<script>
  import axios from "axios";

  export default {
    data: function () {
      return {
        newPostParams: {},
        errors: [],
      };
    },
    methods: {
      submit: function () {
        axios
          .post("/posts/new", this.newPostParams)
          .then((response) => {
            console.log(response.data);
            this.$router.push("/login");
          })
          .catch((error) => {
            this.errors = error.response.data.errors;
          });
      },
    },
  };
</script>

<template>
  <div class="posts-new">
    <form v-on:submit.prevent="submit()">
      <h1>Make a New Post</h1>
      <ul>
        <li v-for="error in errors" v-bind:key="error">{{ error }}</li>
      </ul>
      <div>
        <label>user_id:</label>
        <input type="text" v-model="newPostParams.user_id" />
      </div>
      <div>
        <label>title:</label>
        <input type="text" v-model="newPostParams.title" />
      </div>
      <div>
        <label>body:</label>
        <input type="text" v-model="newPostParams.body" />
      </div>
      <div>
        <label>image:</label>
        <input type="image" v-model="newPostParams.image" />
      </div>
      <input type="submit" value="Submit" />
    </form>
  </div>
</template>