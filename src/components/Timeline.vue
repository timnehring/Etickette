<template>
  <div>
    <v-timeline dense>
      <v-timeline-item
        v-for="period in periods"
        :key="period.id"
        :color="circleColor(period.slotsTaken, period.slotsFree)"
      >
        <v-card
        max-width="60vw"
        :disabled="period.slotsFree === period.slotsTaken"
        >
        <v-container class="py-0">
          <v-row>
            <v-col cols="8" class="pa-0">
              <v-card-title class="font-weight-bold title">
                {{ period.timespan }} Uhr
              </v-card-title>
              <v-card-text class="white text--primary">
                <p
                v-if="slotAvailable(period.slotsTaken, period.slotsFree)"
                class="font-weight-bold">
                  {{ period.slotsTaken }} von {{ period.slotsFree }} Plätzen sind belegt.
                </p>
                <p
                v-if="!slotAvailable(period.slotsTaken, period.slotsFree)"
                class="font-weight-bold">
                  Keine Plätze verfügbar.
                </p>
              </v-card-text>
            </v-col>
            <v-col
            cols="4"
            id="btn-col"
            >
                <v-btn
                id="res-btn"
                block
                to="booking"
                :disabled="!slotAvailable(period.slotsTaken, period.slotsFree)"
                class="green">
                <v-icon size="40">mdi-ticket-account</v-icon>
                </v-btn>
            </v-col>
          </v-row>
        </v-container>
        </v-card>
      </v-timeline-item>
    </v-timeline>
  </div>
</template>

<script>
export default ({
  props: ['data'],
  data() {
    return {
      periods: this.data,
    };
  },
  methods: {
    circleColor(val1, val2) {
      let color = '';
      if (val2 === 0 || val1 === val2) {
        color = 'grey';
      } else if (val1 / val2 >= 0.8) {
        color = 'red';
      } else if (val1 / val2 >= 0.5) {
        color = 'orange';
      } else {
        color = 'green';
      }
      return color;
    },
    slotAvailable(val1, val2) {
      let available = true;
      if (val2 === 0) {
        available = false;
      } else if (val1 === val2) {
        available = false;
      } else {
        available = true;
      }
      return available;
    },
  },
});
</script>

<style scoped>
  #res-btn {
    position: relative;
    width: 100%;
    height: 100%;
  }
  #btn-col {
    padding: 0;
  }
</style>
