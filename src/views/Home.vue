<template>
  <div class="home">
    <ShopGrid/>
  </div>
</template>

<script>
// @ is an alias to /src
import ShopGrid from '@/components/ShopGrid.vue';

export default {
  name: 'Home',
  components: {
    ShopGrid,
  },
};
</script>
