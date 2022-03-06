<template>
  <v-container>
    <v-row text-center justify-center>
      <v-col class="cols-12">
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
      <v-col cols-12 class="mb-2">
        <main class="cardRow">
          <h1>Random Users:</h1>
        </main>
      </v-col>
    </v-row>

    <v-row justify-center>
      <v-col class="col-12 col-sm-6 col-md-4" v-for="(user, i) in users" :key="i">
        <v-card pa-2 shaped max-width="400">
          <v-card-title>{{ user.name }}</v-card-title>

          <v-divider></v-divider>

          <v-card-text>
            <p>E-mail Address: </p>
            <p>Phone Number: {{user.phone}}</p>
            <p>Street: {{user.address.street}}</p>
            <p>City: {{user.address.city}}</p>
            <p>Zipcode: {{user.address.zipcode}}</p>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

// &#128512;

<script>
export default {
  name: "MainPage",
  data() {
    return {
      users: [],
    };
  },
  mounted() {
    this.$http
      .get("https://jsonplaceholder.typicode.com/users")
      .then(function (data) {
        this.users = data.body.slice(0, 9);
      });
  },
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
