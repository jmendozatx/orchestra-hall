<template>
  <v-app>
    <v-app-bar flat color="#f5f5f5" app>
      <v-img
        alt="Bob's Orchestra Hall Logo"
        contain
        :src="require('@/assets/logo.png')"
        transition="scale-transition"
        max-width="175"
      />
      <v-spacer></v-spacer>
      <v-btn text>
        <span class="mr-2">Login</span>
      </v-btn>
    </v-app-bar>

    <v-main>
      <EventPage />
    </v-main>
  </v-app>
</template>

<script>
import EventPage from "./views/EventPage.vue";

export default {
  name: "App",

  components: {
    EventPage,
  },

  data: () => ({
    //
  }),
};
</script>

<style>
.v-main {
  background: #f5f5f5;
}
</style>
