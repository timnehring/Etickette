<template>
  <div class="about">
    <v-stepper v-model="e1">
    <v-stepper-header>
      <v-stepper-step :complete="e1 > 1" step="1">Erklärung</v-stepper-step>

      <v-divider></v-divider>

      <v-stepper-step :complete="e1 > 2" step="2">Angabe der Daten</v-stepper-step>

      <v-divider></v-divider>

      <v-stepper-step step="3">Bestätigung</v-stepper-step>
    </v-stepper-header>

    <v-stepper-items>
      <v-stepper-content step="1">
        <v-card
          class="mb-12"
          color="grey lighten-1"
          height="200px"
        ></v-card>

        <v-btn
          color="primary"
          @click="e1 = 2"
        >
          Weiter
        </v-btn>

        <v-btn text to="shop">Abbrechen</v-btn>
      </v-stepper-content>

      <v-stepper-content step="2">
        <v-card
          class="mb-12"
          color="grey lighten-1"
          height="200px"
        >
          <v-form v-model="valid">
            <v-container>
              <v-row>
                <v-col
                  cols="12"
                  md="4"
                >
                  <v-text-field
                    v-model="firstname"
                    :rules="nameRules"
                    label="Vorname"
                    required
                  ></v-text-field>
                </v-col>

                <v-col
                  cols="12"
                  md="4"
                >
                  <v-text-field
                    v-model="lastname"
                    :rules="nameRules"
                    label="Nachname"
                    required
                  ></v-text-field>
                </v-col>
              </v-row>
            </v-container>
          </v-form>
        </v-card>

        <v-btn
          color="primary"
          @click="e1 = 3"
        >
          Weiter
        </v-btn>

        <v-btn text to="shop">Abbrechen</v-btn>
      </v-stepper-content>

      <v-stepper-content step="3">
        <v-card
          class="mb-12"
          color="grey lighten-1"
          height="200px"
        ></v-card>

        <v-btn
          color="primary"
          to="/"
        >
          Beenden
        </v-btn>
      </v-stepper-content>
    </v-stepper-items>
  </v-stepper>
  </div>
</template>

<script>
export default {
  data() {
    return {
      e1: 1,
      firstname: '',
      lastname: '',
    };
  },
};
</script>
