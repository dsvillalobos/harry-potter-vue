<script setup>
import { onMounted, ref } from "vue";
import { useRoute } from "vue-router";
import axios from "axios";
import NavigationBar from "@/components/NavigationBar.vue";

const route = useRoute();
const characterId = route.params.id;
const character = ref([]);

onMounted(async function () {
  try {
    const response = await axios.get(
      `https://hp-api.onrender.com/api/character/${characterId}`
    );
    character.value = response.data;
  } catch (err) {
    console.log(err);
  }
});
</script>

<template>
  <NavigationBar></NavigationBar>
  <main class="container text">
    <div class="col-md-8 mx-auto">
      <div v-for="char in character">
        <div class="row">
          <div class="col-md-4 mb-3 text-center">
            <img class="rounded" :src="char.image" :alt="char.name" />
          </div>
          <div class="col-md-8 mb-3 text-center">
            <h5 class="mb-2">{{ char.name }}</h5>
            <ul class="list-group list-group-flush mx-3 small">
              <li class="list-group-item text">
                <b>Species: </b>{{ char.species }}
              </li>
              <li class="list-group-item text">
                <b>Gender: </b>{{ char.gender }}
              </li>
              <li class="list-group-item text">
                <b>House: </b>{{ char.house }}
              </li>
              <li class="list-group-item text">
                <b>Date of Birth: </b>{{ char.dateOfBirth }}
              </li>
              <li v-if="char.wizard == true" class="list-group-item text">
                Wizard
              </li>
              <li class="list-group-item text">
                <b>Ancestry: </b>{{ char.ancestry }}
              </li>
              <li class="list-group-item text">
                <b>Eye Color: </b>{{ char.eyeColour }}
              </li>
              <li class="list-group-item text">
                <b>Hair Color: </b>{{ char.hairColour }}
              </li>
              <li class="list-group-item text">
                <b>Patronus: </b>{{ char.patronus }}
              </li>
              <li
                v-if="char.hogwartsStudent == true"
                class="list-group-item text"
              >
                Hogwarts Student
              </li>
              <li
                v-if="char.hogwartsStaff == true"
                class="list-group-item text"
              >
                Hogwarts Staff
              </li>
              <li class="list-group-item text">
                <b>Actor: </b>{{ char.actor }}
              </li>
              <li class="list-group-item text">
                <b> Status: </b>
                <span v-if="char.alive == true">Alive</span>
                <span v-if="char.alive == false">Dead</span>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
img {
  width: 250px !important;
  height: 350px !important;
  object-fit: cover !important;
  object-position: cover !important;
}

.list-group-item {
  background-color: transparent !important;
}
</style>
