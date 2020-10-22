<template>
  <div class="movies-index">
    <h1>All Movies List</h1>

    <div v-for="movie in movies">
      <h4>Title: {{ movie.title }}</h4>
      <p>Year: {{ movie.year }}</p>
      <p>plot: {{movie.plot }} </p>
      
      <!-- <p>User Id: {{ movie.user_id }}</p> -->
      <router-link :to="`/movies/${movie.id}`">More Info</router-link>


    </div>

  </div>
</template>

<style>
</style>

<script>
import axios from "axios";

export default {
  data: function () {
    return {
      movies: [],
    };
  },
  created: function () {
    axios.get("/api/movies").then((response) => {
      console.log(response.data);
      this.movies = response.data;
    });
  },
  methods: {},
};
</script>