<template>
  <v-app>
    <AppHeader/>
    <v-main>
<!--      <v-container fill-height fluid>-->
<!--        <v-row align="center"-->
<!--               justify="center">-->
<!--          <v-col>-->
<!--            <v-card-->
<!--                class="mx-auto"-->
<!--                outlined-->
<!--                color="red"-->
<!--                height="500px"-->
<!--                width="1200px"-->
<!--            >-->
<!--            </v-card>-->
<!--          </v-col>-->
<!--        </v-row>-->
<!--      </v-container>-->
      <AppForm/>
    </v-main>
    <AppFooter/>
  </v-app>
</template>

<style>
body {
  margin: 0;
  background: #eee;
}
</style>

<script>
import AppHeader from "@/components/AppHeader";
import AppFooter from "@/components/AppFooter";
import AppForm from "@/components/AppForm";

export default {
  name: 'App',

  components: {
    AppHeader,
    AppFooter,
    AppForm,
  },

  data: () => ({
    //
  }),
};
</script>
