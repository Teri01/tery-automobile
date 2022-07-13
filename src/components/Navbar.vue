<template>
  <nav class="navbar navbar-expand-lg navbar-dark is-visible is-fixed" id="mainNav">
    <div class="container px-4 px-lg-5">
                  <router-link to="/" class="navbar-brand"
              >TeryAutomobile</router-link
            >
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarResponsive"
        aria-controls="navbarResponsive"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        Menu
        <i class="fas fa-bars"></i>
      </button>
      <div class="collapse navbar-collapse" id="navbarResponsive">
        <ul class="navbar-nav ms-auto py-4 py-lg-0">
                  <li class="nav-item">
            <router-link to="/Add" class="nav-link px-lg-3 py-3 py-lg-4"
              >Adaugare anunt</router-link
            >
          </li>
          <li class="nav-item">
            <router-link to="/list" class="nav-link px-lg-3 py-3 py-lg-4"
              >Anunturi</router-link
            >
          </li>
          <li class="nav-item">
            <router-link to="/about" class="nav-link px-lg-3 py-3 py-lg-4"
              >About</router-link
            >
          </li>
          <li class="nav-item">
            <router-link to="/contact" class="nav-link px-lg-3 py-3 py-lg-4"
              >Contact</router-link
            >
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Navbar",
  watch: {
    $route(to, next) {
        let path = to.fullPath;
        const mainNav = document.getElementById("mainNav");
        if (path.includes("/announcement") || path.includes("/list")) {
          mainNav.classList.add("bg-color-grey");
        } else {
          mainNav.classList.remove("bg-color-grey");
        }
    },
  },
};
</script>

<style scoped>
.bg-color-grey {
  background-color: #f9f9f9 !important;
}
</style>