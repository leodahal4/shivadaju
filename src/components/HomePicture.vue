<template>
  <v-card elevation="10" class="mt-10">
  <v-img
    src="../assets/home4.jpg"
    lazy-src="../assets/home4.jpg"
    class="mt-16 fullscreenImage"
    height="850"
  >
    <template v-slot:placeholder>
      <v-row
        class="fill-height ma-0"
        align="center"
        justify="center"
      >
          <v-progress-circular
            indeterminate
            color="primary"
          ></v-progress-circular>
        </v-row>
      </template>
    <template v-slot:default>
      <v-container
        fluid
      >
        <v-row
          align="center"
          justify="center"
          class="text-h3 white--text mt-10 text-center font-weight-light"
        >
          You're Just a click away from
          <br />
          selling your home
        </v-row>
        <v-row
          align="center"
          justify="center"
        >
          <v-col
            cols="12"
            sm="12"
            md="6"
            xs="12"
            lg="4"
          >
            <v-text-field
              label="Enter your street address"
              placeholder="Enter your street address"
              outlined
              dark
              class="white--text ma-0 pa-0 mt-3"
              rounded
            >
              <template v-slot:append>
                <v-btn
                  color="primary"
                  @click="show"
                  rounded
                  class="mb-4"
                >
                  Claim Fair Offer
                </v-btn>
              </template>
            </v-text-field>
          </v-col>
        </v-row>
        <v-row
          align="center"
          justify="center"
          class="white--text font-weight-bold text-caption text-center"
          no-gutters
        >
          Sell your home to House Buyers of America and avoid the
          <br/>hassle of real estate agents, repairs and months of uncertainty.
        </v-row>
      </v-container>
    </template>
    </v-img>
  </v-card>
</template>

<script>
export default {
  methods: {
    show() {
      console.log("Here it is.")
    }
  }
}
</script>

<style>
.backgroundImage {
  width: 100%;
  height: 70%;
  position: absolute;
  left: 0;
  top: 10%;
  background: url("../assets/home1.jpg") no-repeat center center;
}
.imageHere {
  max-height: 20%!important;
}
.fullscreenImage {
  width: 100%!important;
}
</style>
