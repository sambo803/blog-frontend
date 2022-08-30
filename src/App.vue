<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
      <router-link to="/signup">Signup</router-link> |
      <router-link to="/posts">Posts</router-link>|
      <router-link to="/login">Login</router-link> |
       <router-link to="/logout">logout</router-link> |
       <p><router-link to="/posts/new">New Posts</router-link></p>|
  </nav>
  
  <router-view/>
</template>

<style>

</style>
