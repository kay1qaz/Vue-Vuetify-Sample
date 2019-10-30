<template>
<!--Kay insert v-app tag-->
  <v-app>
  <div id="app">
    <listgraduatesasync caption="Graduate roll"></listgraduatesasync>
  </div>
  </v-app>
</template>

<script>
  import listgraduatesasync from './components/listgraduatesasync.vue';

  export default {
    name: 'app',
    data() {
      return {
        valued: true
      }
    },
    components: {
      listgraduatesasync
    }
  };
</script>

<style>
</style>

