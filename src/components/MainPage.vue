<template>
  <v-card class="mx-auto landingCard" tile>
    <div class="parallax">
      <div class="insideObject tracking-in-expand">Hello guys &#128512;!!!</div>
    </div>

    <v-row class="px-5 grey lighten-1">
      <v-col cols="12">
        <div class="cardTitle">
          <h1 data-aos="zoom-in">Random Users:</h1>
        </div>
      </v-col>
    </v-row>

    <v-row class="grey lighten-1 px-5">
      <v-col
        class="col-12 col-sm-6 col-md-4"
        v-for="(user, i) in users"
        :key="i"
      >
        <v-card class="mx-auto" shaped max-width="400" data-aos="zoom-in">
          <v-card-title>{{ user.name }}</v-card-title>

          <v-divider></v-divider>

          <v-card-text>
            <p>
              <span class="font-weight-bold">E-mail Address:</span>
              {{ user.email }}
            </p>
            <p>
              <span class="font-weight-bold">Phone Number:</span>
              {{ user.phone }}
            </p>
            <p>
              <span class="font-weight-bold">Street:</span>
              {{ user.address.street }}
            </p>
            <p>
              <span class="font-weight-bold">City:</span>
              {{ user.address.city }}
            </p>
            <p>
              <span class="font-weight-bold">Zipcode:</span>
              {{ user.address.zipcode }}
            </p>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-card>
</template>

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
@import url("https://fonts.googleapis.com/css2?family=Permanent+Marker&display=swap");
.insideObject {
  position: absolute;
  top: 40%;
  width: 100%;
  text-align: center;
  font-family: "Permanent Marker", cursive;
  font-size: 50px;
  letter-spacing: 5px;
  font-weight: bold;
  color: white;
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
.cardTitle h1 {
  font-family: "Permanent Marker", cursive;
  color: #424242;
  border-bottom: 3px solid #424242;
}
.landingCard {
  height: 100%;
}
.parallax {
  background-image: url("../assets/backImg.jpg");
  height: 100%;
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}
@media only screen and (max-device-width: 600px) {
  .landingCard {
    height: 40%;
  }
  .insideObject {
    font-size: 20px;
  }
}
@media only screen and (min-device-width: 600px) and (max-device-width: 900px) {
  .landingCard {
    height: 60%;
  }
  .insideObject {
    font-size: 30px;
  }
}
@media only screen and (min-device-width: 900) and (max-device-width: 1200px) {
  .landingCard {
    height: 80%;
  }
  .insideObject {
    font-size: 40px;
  }
}
</style>
