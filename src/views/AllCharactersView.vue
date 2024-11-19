<script setup>
import { onMounted, ref } from "vue";
import axios from "axios";
import NavigationBar from "@/components/NavigationBar.vue";

const characters = ref([]);

onMounted(async function () {
  try {
    const response = await axios.get(
      "https://hp-api.onrender.com/api/characters"
    );
    characters.value = response.data;
  } catch (err) {
    console.log(err);
  }
});
</script>

<template>
  <NavigationBar></NavigationBar>
  <main class="container text">
    <div class="col-md-8 mx-auto">
      <h3 class="text-center mb-4">All Characters</h3>
      <div class="row mb-4">
        <div
          class="col-md-4 mb-4"
          v-for="character in characters"
          :key="character.id"
        >
          <div class="card">
            <img
              v-if="character.image != ''"
              loading="lazy"
              :src="character.image"
              :alt="character.name"
            />
            <div class="card-body">
              <h5 class="card-title text-center">{{ character.name }}</h5>
              <div class="small fst-italic text-center">
                {{ character.actor }}
              </div>
              <div class="d-grid gap-2 my-3">
                <RouterLink
                  class="btn btn-primary btn-sm rounded-pill"
                  :to="'/character/' + character.id"
                  >Details</RouterLink
                >
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
.card {
  height: 450px !important;
}

.card img {
  width: 100% !important;
  height: 300px !important;
  object-fit: cover !important;
  object-position: center !important;
}
</style>
