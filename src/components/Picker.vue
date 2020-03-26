<template>
  <div>
    <v-card color="basil">
      <v-tabs
        v-model="tab"
        grow
        style="position: sticky; top: 0; z-index: 3"
      >
        <v-tab>
          Morgens
        </v-tab>
        <v-tab>
          Nachmittags
        </v-tab>
        <v-tab>
          Abends
        </v-tab>
      </v-tabs>

      <v-tabs-items v-model="tab">
        <v-tab-item>
          <Timeline/>
        </v-tab-item>
        <v-tab-item>
          <Timeline/>
        </v-tab-item>
        <v-tab-item>
          <Timeline/>
        </v-tab-item>
      </v-tabs-items>
    </v-card>
  </div>
</template>

<script>
import Timeline from '@/components/Timeline.vue';

export default {
  components: {
    Timeline,
  },
  data() {
    return {
      tab: null,
    };
  },
};
</script>
