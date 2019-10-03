<template>
  <v-app id="inspire">
      <navbar/>
  </v-app>
</template>

<script>
import navbar from './components/Navbar';

export default {
  name: 'App',
  components: {
    navbar,
  },
};
</script>
<style scoped>
body {
  overflow-x: hidden;
}
</style>
