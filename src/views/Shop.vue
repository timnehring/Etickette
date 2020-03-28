<template>
  <div class="shop">
    <ShopProfile/>
    <Picker/>
  </div>
</template>

<script>
import ShopProfile from '@/components/ShopProfile.vue';
import Picker from '@/components/Picker.vue';

export default {
  name: 'Shop',
  components: {
    ShopProfile,
    Picker,
  },
};
</script>
