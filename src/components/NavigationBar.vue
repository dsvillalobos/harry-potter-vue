<script setup>
import { RouterLink } from "vue-router";
</script>

<template>
  <header class="sticky-top mb-4">
    <nav class="navbar header-color navbar-dark">
      <div class="container-fluid">
        <RouterLink class="navbar-brand fs-2 fw-bold" to="/"
          >Harry Potter | Guide</RouterLink
        >
        <button
          class="navbar-toggler border-0"
          type="button"
          data-bs-toggle="offcanvas"
          data-bs-target="#offcanvasNavbar"
          aria-controls="offcanvasNavbar"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div
          class="offcanvas header-color offcanvas-end"
          tabindex="-1"
          id="offcanvasNavbar"
          aria-labelledby="offcanvasNavbarLabel"
        >
          <div class="offcanvas-header p-0 justify-content-end">
            <button
              type="button"
              class="btn text-light fs-4"
              data-bs-dismiss="offcanvas"
              aria-label="Close"
            >
              X
            </button>
          </div>
          <div class="offcanvas-body pt-0 ms-2">
            <ul class="navbar-nav justify-content-end flex-grow-1 pe-3">
              <li class="nav-item mb-2">
                <RouterLink class="nav-link text-light" to="/">Home</RouterLink>
              </li>
              <li class="nav-item my-2">
                <RouterLink class="nav-link text-light" to="/all-characters"
                  >All Characters</RouterLink
                >
              </li>
              <li class="nav-item my-2">
                <RouterLink class="nav-link text-light" to="/all-hogwarts-staff"
                  >All Hogwarts Staff</RouterLink
                >
              </li>
              <li class="nav-item my-2">
                <RouterLink class="nav-link text-light" to="/about"
                  >About</RouterLink
                >
              </li>
            </ul>
          </div>
        </div>
      </div>
    </nav>
  </header>
</template>

<style scoped>
.header-color {
  background-color: #617c94 !important;
}

.navbar button {
  outline: none !important;
  box-shadow: none !important;
}
</style>
