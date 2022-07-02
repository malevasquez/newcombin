<template>
  <v-footer class="footer"
      color="#006CBF"
      padless

  >
    <v-row class="pa-4 mx-8"
        no-gutters
    >
      copyright
      <v-spacer></v-spacer>
      All rights reserved
    </v-row>
  </v-footer>
</template>

<script>
export default {
  name: "AppFooter"
}
</script>

<style scoped>
  .footer {
    bottom: 0;
    position: sticky;
    height: auto;
  }
  .v-btn {
    text-transform: none !important;
  }
</style>