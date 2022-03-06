<template>
  <v-app>
    <v-container class="pa-0" fluid>
      <v-row class="justify-center main">
        <v-col cols="12" class="pb-0">
          <MainPage />
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<script>
import MainPage from "./components/MainPage";

export default {
  name: "App",

  components: {
    MainPage,
  },

  data: () => ({
    //
  }),
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap");

.main {
  font-family: "Poppins", sans-serif;
}
</style>
