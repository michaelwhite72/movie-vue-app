<template>
  <div id="app">
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/movies">MoviesIndex</router-link> |
      <router-link to="/movies/new">MoviesNew</router-link> |
      <span v-if="isLoggedIn()">
        <router-link to="/logout">Logout</router-link>
      </span>
      <span v-else>
        <router-link to="/signup">Signup</router-link> |
        <router-link to="/login">Login</router-link>
      </span>
    </div> -->
    <!-- <router-view /> -->
    <header id="header">
      <a href="index.html" class="logo">MOVIE APP</a>
    </header>

    <nav id="nav">
      <ul class="links">
        <li class="active"><a href="index.html">Home</a></li>
        <li><a href="/movies">MoviesIndex</a></li>
        <li><a href="/movies/new">MoviesNew</a></li>
      </ul>
      <ul class="icons">
        <li>
          <a href="#" class="icon brands fa-twitter"
            ><span class="label">Twitter</span></a
          >
        </li>
        <li>
          <a href="#" class="icon brands fa-facebook-f"
            ><span class="label">Facebook</span></a
          >
        </li>
        <li>
          <a href="#" class="icon brands fa-instagram"
            ><span class="label">Instagram</span></a
          >
        </li>
        <li>
          <a href="#" class="icon brands fa-github"
            ><span class="label">GitHub</span></a
          >
        </li>
      </ul>
    </nav>

    <router-view />

    <footer id="footer" class="midnight-blue">
      <footer id="footer">
        <section>
          <form method="post" action="#">
            <div class="fields">
              <div class="field">
                <label for="name">Name</label>
                <input type="text" name="name" id="name" />
              </div>
              <div class="field">
                <label for="email">Email</label>
                <input type="text" name="email" id="email" />
              </div>
              <div class="field">
                <label for="message">Message</label>
                <textarea name="message" id="message" rows="3"></textarea>
              </div>
            </div>
            <ul class="actions">
              <li><input type="submit" value="Send Message" /></li>
            </ul>
          </form>
        </section>
        <section class="split contact">
          <section class="alt">
            <h3>Address</h3>
            <p>
              1234 Somewhere Road #87257<br />
              Nashville, TN 00000-0000
            </p>
          </section>
          <section>
            <h3>Phone</h3>
            <p><a href="#">(000) 000-0000</a></p>
          </section>
          <section>
            <h3>Email</h3>
            <p><a href="#">info@untitled.tld</a></p>
          </section>
          <section>
            <h3>Social</h3>
            <ul class="icons alt">
              <li>
                <a href="#" class="icon brands alt fa-twitter"
                  ><span class="label">Twitter</span></a
                >
              </li>
              <li>
                <a href="#" class="icon brands alt fa-facebook-f"
                  ><span class="label">Facebook</span></a
                >
              </li>
              <li>
                <a href="#" class="icon brands alt fa-instagram"
                  ><span class="label">Instagram</span></a
                >
              </li>
              <li>
                <a href="#" class="icon brands alt fa-github"
                  ><span class="label">GitHub</span></a
                >
              </li>
            </ul>
          </section>
        </section>
      </footer>
    </footer>
    <!--/#footer-->
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      flashMessage: "",
    };
  },

  methods: {
    isLoggedIn: function() {
      return localStorage.getItem("jwt");
    },
    getUserId: function() {
      return localStorage.getItem("user_id");
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: green;
}
/* #nav {
  padding: 30px;
} */
#nav a {
  font-weight: bold;
  color: white;
}
#nav a.router-link-exact-active {
  color: red;
}
h1 {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: green;
}
h2 {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: green;
}
.button {
  color: red;
}
</style>
