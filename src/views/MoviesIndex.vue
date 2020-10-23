<template>
  <div class="movies-index">
    <h1>All Movies List</h1>

    <div>
      <button>Sort Alphabetically</button>
    </div>

    Search by title: <input v-model="titleFilter" list="titles" />
    <datalist id="titles">
      <option v-for="movie in movies">{{ movie.title }}</option>
    </datalist>
    <div
      v-for="movie in orderBy(filterBy(movies, titleFilter, 'title'), 'title')"
    >
      <h4>Title: {{ movie.title }}</h4>
      <p>Year: {{ movie.year }}</p>
      <p>plot: {{ movie.plot }}</p>

      <!-- <p>User Id: {{ movie.user_id }}</p> -->
      <router-link :to="`/movies/${movie.id}`">More Info</router-link>
    </div>
  </div>
</template>

<style></style>

<script>
import axios from "axios";
import Vue2Filters from "vue2-filters";

export default {
  mixins: [Vue2Filters.mixin],
  data: function() {
    return {
      movies: [],
      titleFilter: "",
    };
  },
  created: function() {
    axios.get("/api/movies").then((response) => {
      console.log(response.data);
      this.movies = response.data;
    });
  },
  methods: {},
};
</script>
