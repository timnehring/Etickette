<template>
  <div>
    <v-container style="background-color: #124F6C; height: 10vh;">
      <v-row justify="center" align="center">
        <v-col cols="auto">
          <v-text-field
            label="Postleitzahl"
            type=""
            outlined
            dark
            clearable
            prepend-inner-icon="mdi-map-marker"
            v-model="plz"
          ></v-text-field>
        </v-col>
      </v-row>
    </v-container>
    <v-container>
      <v-row>
          <v-col cols="12" v-for="shop in shops" :key="shop.name">
              <v-card to="shop">
                  <v-card-title class="font-weight-bold title">
                      {{ shop.name }}
                  </v-card-title>
                  <v-container class="py-0">
                      <v-row>
                          <v-col cols="6">
                              <v-img
                              contain
                              :src="shop.logo"
                              height="10vh"></v-img>
                          </v-col>
                          <v-col cols="6">
                              <v-card-text>
                                  <p>
                                      <v-icon>mdi-tag</v-icon>
                                      {{ shop.industry }}
                                  </p>
                                  <p>
                                      {{ shop.totalSpace }} Plätze frei
                                  </p>
                              </v-card-text>
                          </v-col>
                      </v-row>
                  </v-container>
              </v-card>
          </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showAll: true,
      plz: '',
      shops: [
        {
          name: 'REWE Niederpreis',
          plz: '59581',
          industry: 'Lebensmittel',
          logo: 'https://upload.wikimedia.org/wikipedia/commons/4/4c/Logo_REWE.svg',
          totalSpace: '70',
        },
        {
          name: 'Südtor Apotheke',
          plz: '59581',
          industry: 'Apotheke',
          logo: 'https://upload.wikimedia.org/wikipedia/commons/thumb/e/eb/Deutsche_Apotheke_Logo.svg/2000px-Deutsche_Apotheke_Logo.svg.png',
          totalSpace: '30',
        },
        {
          name: 'EDEKA Kauflust',
          plz: '59581',
          industry: 'Lebensmittel',
          logo: 'https://www.banklocator.de/uploads/banks/121.jpg',
          totalSpace: '65',
        },
        {
          name: 'Rossmann',
          plz: '59581',
          industry: 'Drogerie',
          logo: 'https://upload.wikimedia.org/wikipedia/commons/thumb/8/8e/Rossmann_Logo.svg/2000px-Rossmann_Logo.svg.png',
          totalSpace: '54',
        },
      ],
    };
  },
};
</script>
