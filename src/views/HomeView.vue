<script setup>
import { ref } from "vue";
import axios from "axios";
import NavigationBar from "@/components/NavigationBar.vue";

const email = ref("");
const password = ref("");
const user = {
  email: "dsvillacorta@gmail.com",
  password: "Hola12345",
};

function signIn() {
  try {
    if (
      email.value.trim() == user.email &&
      password.value.trim() == user.password
    ) {
      alert("Sign In Successful :)");
    } else {
      alert("Wrong Email or Password :(");
    }
  } catch (err) {
    console.log(err);
  }
}
</script>

<template>
  <NavigationBar></NavigationBar>
  <main class="container text">
    <div class="col-md-8 mx-auto">
      <h3 class="text-center mb-2">Welcome</h3>
      <div class="small text-center mb-4">See if you're registered</div>
      <form class="mx-3" autocomplete="off" @submit.prevent="signIn">
        <div class="mb-3">
          <label for="email" class="form-label">Email:</label>
          <input
            type="email"
            name="email"
            id="email"
            class="form-control"
            required
            v-model="email"
          />
        </div>
        <div class="mb-3">
          <label for="password">Password:</label>
          <input
            type="password"
            name="password"
            id="password"
            class="form-control"
            required
            v-model="password"
          />
        </div>
        <div class="mb-3 d-grid gap-2">
          <button class="btn btn-primary btn-sm rounded-pill">Sign In</button>
        </div>
      </form>
    </div>
  </main>
</template>
