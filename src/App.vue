<template>
  <v-app>
    <AppHeader/>
    <v-main>
      <div class="container">
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
      </div>
    </v-main>
    <AppFooter/>
  </v-app>
</template>

<style>
body {
  margin: 0;
  background: #eee;
}

.container {
  background-color: red;
  overflow: hidden;
  display: flex;
  text-align: center;
  align-content: center;
  width: 90%;
  height: 85%;
  margin-top: 15px;
  margin-bottom: 15px
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
