<template>
  <div class="posts-new">
    <img v-if="status" :src="`https://http.cat/${status}`" alt="">
    <!-- <img v-if="status" :src="`https://i.gifer.com/origin/3a/3a46f339ccec5c45982bcd964f9e887f_w200.gif`" alt=""> -->
    <form v-on:submit.prevent="createPost()">
      <h1>New Movie</h1>
      <ul>
        <li class="text-danger" v-for="error in errors">{{ error }}</li>
      </ul>
      <div class="form-group">
        <label>Title:</label> 
        <input type="text" class="form-control" v-model="title">
      </div>
      <div class="form-group">
        <label>Year:</label>
        <input type="text" class="form-control" v-model="year">
      </div>
      <div class="form-group">
        <label>Plot:</label>
        <input type="text" class="form-control" v-model="plot">
      </div>

      <input type="submit" class="btn btn-primary" value="Submit">
    </form>


  </div>
</template>

<script>
import axios from "axios";

export default {
  data: function () {
    return {
      title: "",
      year: "",
      plot: "",
      // userId: "",
      errors: [],
      status: "",
    };
  },
  methods: {
    createPost: function () {
      var params = {
        title: this.title,
        year: this.year,
        plot: this.plot,
        // user_id: this.passwordConfirmation,
      };
      axios
        .post("/api/movies", params)
        .then((response) => {
          this.$router.push("/movies");
        })
        .catch((error) => {
          this.errors = error.response.data.errors;
          this.status = error.response.status;
        });
    },
  },
};
</script>
