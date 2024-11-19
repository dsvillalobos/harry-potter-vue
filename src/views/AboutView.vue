<script setup>
import NavigationBar from "@/components/NavigationBar.vue";
</script>

<template>
  <NavigationBar></NavigationBar>
  <main class="container text">
    <div class="col-md-8 mx-auto">
      <h3 class="text-center mb-4">About</h3>
      <div class="small mb-3">
        Welcome to Harry Potter Guide—your magical gateway to the world of Harry
        Potter, optimized for lightning-fast performance! Crafted with
        cutting-edge technologies like Vue and Vite, this Progressive Web App
        (PWA) is designed to deliver an unparalleled user experience right from
        the startup. Our mission? To ensure that every Harry Potter fan has
        instant access to a comprehensive guide of characters, Hogwarts staff,
        and spells, all packaged within a sleek and responsive interface.
      </div>
      <h5 class="text-center">Technical Features</h5>
      <div class="small mb-3">
        <ul class="list-group list-group-flush">
          <li class="list-group-item text">
            <b>Built with Vue and Vite: </b>Leveraging modern frameworks for
            optimal performance.
          </li>
          <li class="list-group-item text">
            <b>Packaged as a PWA: </b>Installable on iOS, Android, Windows, and
            MacOS for a seamless experience across devices.
          </li>
          <li class="list-group-item text">
            <b>Bootstrap Integration: </b>Aesthetic and functional design with a
            custom theme for a unique look and feel.
          </li>
          <li class="list-group-item text">
            <b>API-Driven: </b>Powered by the Harry Potter API for dynamic and
            up-to-date information.
          </li>
          <li class="list-group-item text">
            <b>HTTP Requests with Axios: </b>Efficient and organized data
            management.
          </li>
          <li class="list-group-item text">
            <b>High Performance: </b>Fast startup times using advanced caching
            and loading strategies.
          </li>
        </ul>
      </div>
    </div>
  </main>
</template>

<style scoped>
.list-group-item {
  background-color: transparent !important;
}
</style>
