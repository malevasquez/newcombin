<template>
  <v-app>
    <AppHeader/>
    <v-main>
    </v-main>
    <AppFooter/>
  </v-app>
</template>

<script>
import AppHeader from "@/components/AppHeader";
import AppFooter from "@/components/AppFooter";

export default {
  name: 'App',

  components: {
    AppHeader,
    AppFooter,
  },

  data: () => ({
    //
  }),
};
</script>
