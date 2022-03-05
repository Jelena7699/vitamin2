<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <header class="imageContainer">
          <v-img
            :src="require('../assets/backImg.jpg')"
            :lazy-src="require('../assets/backImg.jpg')"
          ></v-img>
          <div class="insideObject tracking-in-expand">Hello guys !!!</div>
        </header>
      </v-col>
    </v-row>

    <v-row>
      <v-col cols-12 class="mb-2" style="border: 1px solid black">
        <main class="cardRow">
          <h1>Random Users:</h1>
        </main>
      </v-col>
    </v-row>
  </v-container>
</template>

// &#128512;

<script>
export default {
  name: "MainPage",

  data: () => ({
    //
  }),
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Permanent+Marker&display=swap");

.container {
  max-width: 100%;
  font-family: "Poppins", sans-serif;
}
.imageContainer {
  position: relative;
  height: 400px;
  color: white;
  overflow: hidden;
}
.imageContainer img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.insideObject {
  position: absolute;
  top: 40%;
  width: 100%;
  text-align: center;
  font-family: "Permanent Marker", cursive;
  font-size: 50px;
  letter-spacing: 5px;
  font-weight: bold;
}
.tracking-in-expand {
  -webkit-animation: tracking-in-expand 2s cubic-bezier(0.215, 0.61, 0.355, 1)
    0.5s both;
  animation: tracking-in-expand 2s cubic-bezier(0.215, 0.61, 0.355, 1) 0.5s both;
}
@-webkit-keyframes tracking-in-expand {
  0% {
    letter-spacing: -0.5em;
    opacity: 0;
  }
  40% {
    opacity: 0.6;
  }
  100% {
    opacity: 1;
  }
}
@keyframes tracking-in-expand {
  0% {
    letter-spacing: -0.5em;
    opacity: 0;
  }
  40% {
    opacity: 0.6;
  }
  100% {
    opacity: 1;
  }
}
.cardRow h1 {
  font-family: "Permanent Marker", cursive;
  color: #424242;
  border-bottom: 3px solid #424242;
}
</style>
