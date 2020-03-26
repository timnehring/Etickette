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
  data() {
    return {
      periods: [
        {
          id: 1,
          timespan: '08-09',
          slotsTaken: 42,
          slotsFree: 50,
        },
        {
          id: 2,
          timespan: '09-10',
          slotsTaken: 6,
          slotsFree: 50,
        },
        {
          id: 3,
          timespan: '10-11',
          slotsTaken: 36,
          slotsFree: 50,
        },
        {
          id: 4,
          timespan: '11-12',
          slotsTaken: 12,
          slotsFree: 30,
        },
        {
          id: 5,
          timespan: '12-13',
          slotsTaken: 25,
          slotsFree: 50,
        },
        {
          id: 6,
          timespan: '13-14',
          slotsTaken: 0,
          slotsFree: 0,
        },
        {
          id: 7,
          timespan: '14-15',
          slotsTaken: 50,
          slotsFree: 50,
        },
        {
          id: 8,
          timespan: '15-16',
          slotsTaken: 16,
          slotsFree: 50,
        },
        {
          id: 9,
          timespan: '16-17',
          slotsTaken: 6,
          slotsFree: 50,
        },
        {
          id: 10,
          timespan: '17-18',
          slotsTaken: 5,
          slotsFree: 20,
        },
        {
          id: 11,
          timespan: '18-19',
          slotsTaken: 6,
          slotsFree: 50,
        },
        {
          id: 12,
          timespan: '19-20',
          slotsTaken: 43,
          slotsFree: 50,
        },
        {
          id: 13,
          timespan: '20-21',
          slotsTaken: 14,
          slotsFree: 50,
        },
      ],
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
