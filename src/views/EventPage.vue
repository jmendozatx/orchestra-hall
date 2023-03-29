<template>
  <div class="events-page">
    <Hero :event="event" />
    <v-container>
      <v-row>
        <v-col>
          <span>{{ event.Description }}</span>
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <h2>Upcoming Events</h2>
          <span class="subtitle-2">All times are listed in Seattle, WA local time</span>
        </v-col>
      </v-row>
      <v-row v-for="(date, index) in event.Dates" :key="index">
        <v-col>
          <EventCard :date="date" />
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import data from "@/assets/data.json";
import Hero from "@/components/Hero.vue";
import EventCard from "@/components/EventCard.vue";

export default {
  name: "EventPage",
  data() {
    return {
      event: data[0],
    };
  },

  components: {
    Hero,
    EventCard,
  },
};
</script>

<style lang="scss">
</style>