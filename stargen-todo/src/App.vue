<template lang="pug">
  <div>
    v-app
      Navbar
      v-content
        router-view
          
  </div>
</template>

<script>

import Navbar from '@/components/Navbar.vue'

export default {
  name: 'App',
  components: {
    Navbar
  },
  data: () => ({
    //
  }),
};
</script>
