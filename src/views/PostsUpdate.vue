<script>
  import axios from 'axios';
  
    export default {
      data: function () {
        return {
          message: "Welcome to Vue Update!!.js!",
          update: {}
        };
      },
      created: function () {
        this.PostUpdate();
      },
      methods: {
        PostShow: function () {
          console.log('update post..');
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
    <div class="posts-update">
      <h3>{{ message }}</h3>
  
   </div>
  </template>
  
  <style></style>