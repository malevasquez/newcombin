<template>
  <v-app>
    <AppHeader/>
    <v-main>
      <v-container fluid>
        <v-row>
          <v-col>
            <AppForm/>
          </v-col>
          <v-col>
            <AppTable/>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
    <AppFooter/>
  </v-app>
</template>

<style>
body {
  margin: 0;
  background: #eee;
}

v-container {
  background-color: red;
}

.box {
  width: 500px;
  height: 500px;
  background-color: red;
  text-align: center;
  vertical-align: center;
}
</style>

<script>
import AppHeader from "@/components/AppHeader";
import AppFooter from "@/components/AppFooter";
import AppForm from "@/components/AppForm";
import AppTable from "@/components/AppTable";

export default {
  name: 'App',

  components: {
    AppHeader,
    AppFooter,
    AppForm,
    AppTable,
  },

  data: () => ({
    //
  }),
};
</script>
