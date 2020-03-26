<template>
  <div>
    <v-container style="background-color: #124F6C; height: 150px;"></v-container>
      <v-card class="pa-0 ma-0">
        <v-container class="pa-0">
          <v-row justify="center" class="ma-0">
            <v-col cols="auto" class="pa-0">
              <v-avatar
              color="#50B5CE"
              size="100">
                <v-icon size="60" dark>mdi-cart</v-icon>
              </v-avatar>
            </v-col>
          </v-row>
          <v-row justify="center" class="ma-0">
            <v-col cols="auto" class="pb-0">
              <v-card-text class="font-weight-bold title">
                Shop Name
              </v-card-text>
            </v-col>
          </v-row>
          <v-row justify="center" class="ma-0">
            <v-col cols="auto" class="pt-0">
              <v-card-text class="py-0">
                <v-icon color="red" dense>mdi-map-marker</v-icon>Warstein
              </v-card-text>
            </v-col>
          </v-row>
          <v-divider></v-divider>
          <v-row justify="center" class="ma-0">
            <v-col cols="auto" class="pb-0">
              <v-card-text class="pt-0">
                <p class="font-weight-bold subheadding">Öffnungszeiten</p>
                <span>Mo-Fr: 08:00 Uhr - 21:00 Uhr</span>
                <br>
                <span>Sa: 08:00 Uhr - 13:00 Uhr</span>
              </v-card-text>
            </v-col>
          </v-row>
        </v-container>
      </v-card>
  </div>
</template>

<script>
export default {
  //
};
</script>

<style scoped>
  .v-avatar{
    z-index: 3;
    margin-top: -50px;
  }
</style>
