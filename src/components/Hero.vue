<template>
  <v-parallax :src="event.Image" height="400" class="hero">
    <v-container>
      <v-row>
        <v-col cols="12" class="text-center">
          <h1>{{ event.Title }}</h1>
          <p class="subtitle">{{ event.Type }}</p>
        </v-col>
      </v-row>
    </v-container>
  </v-parallax>
</template>

<script>
export default {
  name: "Hero",

  props: {
    event: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style lang="scss">
.hero {
  h1 {
    @media only screen and (min-width: 600px) {
      font-size: 60px;
      line-height: 1em;
      margin-bottom: 0.5em;
    }
  }

  .subtitle {
    @media only screen and (min-width: 600px) {
      font-size: 22px;
      line-height: 1em;
    }
  }
}
</style>