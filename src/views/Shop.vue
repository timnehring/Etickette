<template>
  <div class="shop">
    <Profile/>
    <Picker/>
  </div>
</template>

<script>
import Profile from '@/components/Profile.vue';
import Picker from '@/components/Picker.vue';

export default {
  name: 'Shop',
  components: {
    Profile,
    Picker,
  },
};
</script>
