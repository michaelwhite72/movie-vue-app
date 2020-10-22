<template>
  <div class="movies-show">
  

      <h4>Title: {{ movie.title }} </h4>
      <p>Year: {{ movie.year }} </p>
      <p>Plot: {{ movie.plot }} </p>
    
      <!-- <p>User Id: {{ movie.user_id }}</p> -->

      <router-link :to="`/movies/${movie.id}/edit`">Edit</router-link>  

  </div>
</template>

<style>
</style>

<script>
import axios from "axios";

export default {
  data: function () {
    return {
      movie: {},
    };
  },
  created: function () {
    axios.get(`/api/movies/${this.$route.params.id}`).then((response) => {
      console.log(response.data);
      this.movie = response.data;
    });
  },
  methods: {},
};
</script>