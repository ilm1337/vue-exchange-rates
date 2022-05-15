<script>
import { RouterLink, RouterView } from "vue-router";
export default {
  data: function () {
    return {
      showNav: false,
    };
  },
};
</script>

<template>
  <header>
    <div class="wrapper">
      <nav
        class="navbar has-shadow is-info"
        role="navigation"
        aria-label="main navigation"
      >
        <div class="navbar-brand">
          <a class="navbar-item" href="/"><strong>Exchange Website</strong></a>

          <a
            role="button"
            class="navbar-burger burger"
            aria-label="menu"
            aria-expanded="false"
            data-target="navbarBasicExample"
            @click="showNav = !showNav"
            :class="{ 'is-active': showNav }"
          >
            <span aria-hidden="true"></span>
            <span aria-hidden="true"></span>
            <span aria-hidden="true"></span>
          </a>
        </div>

        <div
          id="navbarBasicExample"
          class="navbar-menu"
          :class="{ 'is-active': showNav }"
        >
          <div class="navbar-start">
            <a href="/" class="navbar-item"> Home </a>
            <a href="/rates" class="navbar-item"> Rates </a>
            <a href="/about" class="navbar-item"> About </a>
          </div>
        </div>
      </nav>
    </div>
  </header>
  <main>
    <div class="main-container"><RouterView /></div>
  </main>
</template>

<style>
@import "https://cdn.jsdelivr.net/npm/bulma@0.9.4/css/bulma.min.css";

header {
  text-align: center;
  background-color: #009fdf;
  color: white;
}
header a {
  color: white;
}
header a:hover {
  color: white;
  text-decoration: underline;
}
main {
  display: flex;
  justify-content: center;
}
.colums-header {
  max-width: 50%;
}
.main-container {
  margin-top: 50px;
}
</style>
