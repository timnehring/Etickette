<template>
  <div>
    <v-timeline dense>
      <v-timeline-item
        v-for="period in periods"
        :key="period.id"
        :color="chooseColor(period.slotsTaken, period.slotsFree)"
      >
        <v-card
          max-width="60vw"
        >
        <v-container class="py-0">
          <v-row>
            <v-col cols="8" class="pa-0">
              <v-card-title class="font-weight-bold title">
                {{ period.timespan }} Uhr
              </v-card-title>
              <v-card-text class="white text--primary">
                <p v-if="period.slotsFree !== 0" class="font-weight-bold">
                  {{ period.slotsTaken }} von {{ period.slotsFree }} Plätzen sind belegt.
                </p>
                <p v-if="period.slotsFree === 0" class="font-weight-bold">
                  Für diese Zeitspanne werden keine Plätze vergeben.
                </p>
              </v-card-text>
            </v-col>
            <v-col cols="4" class="green">
                <v-btn
                id="res-btn"
                icon
                to="booking">
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
    chooseColor(val1, val2) {
      let color = '';
      if (val1 / val2 >= 0.8 || val2 === 0) {
        color = 'red';
      } else if (val1 / val2 >= 0.5) {
        color = 'orange';
      } else {
        color = 'green';
      }
      return color;
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
</style>
