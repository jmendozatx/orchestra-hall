<template>
  <v-card class="pa-4 event-card">
    <div class="information">
      <div class="date-block">
        <span class="month">{{ time.month }}</span>
        <span class="day">{{ time.day }}</span>
      </div>
      <div class="time-block">
        <div>
          <strong>Time:</strong>
          <span class="time">{{ time.time }}</span>
        </div>
      </div>
    </div>
    <div class="actions">
      <v-btn class="mr-4">
        <v-icon dark left>mdi-ticket-confirmation</v-icon>See Tickets
      </v-btn>
      <v-btn class="mr-4">
        <v-icon dark left>mdi-calendar</v-icon>Add to Calendar
      </v-btn>
    </div>
  </v-card>
</template>

<script>
export default {
  name: "Event",

  data() {
    return {
      timeZone: "America/Los_Angeles",
    };
  },

  props: {
    date: {
      type: String,
      required: true,
    },
  },

  computed: {
    time() {
      const dateObj = new Date(this.date);
      return {
        day: dateObj.toLocaleString("en-US", {
          timeZone: this.timeZone,
          day: "numeric",
        }),
        month: dateObj.toLocaleString("en-US", {
          timeZone: this.timeZone,
          month: "short",
        }),
        time: dateObj.toLocaleString("en-US", {
          timeZone: this.timeZone,
          hour: "numeric",
          minute: "numeric",
          hour12: true,
        }),
      };
    },
  },
};
</script>

<style lang="scss">
.event-card {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-direction: column;

  @media only screen and (min-width: 600px) {
    flex-direction: row;
  }

  .information {
    display: flex;
    align-items: center;
    flex-direction: column;

    @media only screen and (min-width: 600px) {
      flex-direction: row;
    }
  }

  .date-block {
    display: flex;
    flex-direction: row;
    font-size: 2rem;
    font-weight: bold;
    line-height: 1em;

    @media only screen and (min-width: 600px) {
      flex-direction: column-reverse;
    }

    .month {
      margin-right: 10px;
      line-height: 1em;
      text-transform: uppercase;

      @media only screen and (min-width: 600px) {
        font-size: 1rem;
        margin: 0;
      }
    }
  }

  .time-block {
    flex: 1;
    margin: 0 10px 0 20px;

    .time {
      margin-left: 10px;
    }
  }

  .actions {
    text-align: center;

    .v-btn {
      margin-top: 0.75em;
      background-color: #1f2023 !important;
      color: #fff;
      width: 100%;

      @media only screen and (min-width: 600px) {
        margin-top: 0;
        width: inherit;
      }
    }
  }
}
</style>

