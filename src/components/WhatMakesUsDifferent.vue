<template>
  <v-row>
    <v-card
      color="primary"
      class="ma-5 pa-5 font-weight-light"
      width="100%"
      elevation="10"
    >
      <v-col cols="12">
        <v-row align="center" justify="center">
          <v-col cols="12">
            <div class="text-h3 font-weight-thin">
              What Makes Us <span class="white--text">Different</span>
            </div>
          </v-col>
        </v-row>
        <v-row align="center" justify="center">
          <v-col cols="12">
            <hr class="style14" />
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="6">
            <v-row align="center" justify="center">
              <v-col cols="2" class="text-center">
                <v-btn dense depressed icon dark large>
                  <v-icon x-large dark> mdi-hand-heart-outline </v-icon>
                </v-btn>
              </v-col>
              <v-col cols="10">
                <span class="white--text text-h5 font-weight-light"
                  >Stress-Free Sale</span
                >
                <p class="mt-5 font-weight-light">
                  When you work with us, you will be selling without the hassle
                  of expensive repairs, paying commissions, waiting to find a
                  qualified buyer, cleaning out the house or long drawn-out
                  negotiations. It couldn't be easier!
                </p>
              </v-col>
            </v-row>
            <v-row align="center" justify="center">
              <v-col cols="2" class="text-center">
                <v-btn dense depressed icon dark large>
                  <v-icon x-large dark> mdi-cash-multiple </v-icon>
                </v-btn>
              </v-col>
              <v-col cols="10">
                <span class="white--text text-h5 font-weight-light">
                  We Offer Transparent Pricing
                </span>
                <p class="mt-5 font-weight-light">
                  We help you understand how our offer differs from what you
                  would receive if you sold your house with a traditional real
                  estate agent. You’ll get a fair cash offer for your house
                  as-is.
                </p>
              </v-col>
            </v-row>
          </v-col>
          <v-col cols="6">
            <v-row align="center" justify="center">
              <v-col cols="2" class="text-center">
                <v-btn dense depressed icon dark large>
                  <v-icon x-large dark> mdi-timelapse </v-icon>
                </v-btn>
              </v-col>
              <v-col cols="10">
                <span class="white--text text-h5 font-weight-light"
                  >We Close On Your Time Frame</span
                >
                <p class="mt-5 font-weight-light">
                  We purchase your house for cash! You get your money quickly
                  with a fast settlement or simply put your home under contract
                  and schedule a settlement down the road, at your convenience.
                </p>
              </v-col>
            </v-row>
            <v-row align="center" justify="center">
              <v-col cols="2" class="text-center">
                <v-btn dense depressed icon dark large>
                  <v-icon x-large dark> mdi-home-switch </v-icon>
                </v-btn>
              </v-col>
              <v-col cols="10">
                <span class="white--text text-h5 font-weight-light"
                  >We Help You Move</span
                >
                <p class="mt-5 font-weight-light">
                  Our priority is to make the selling process as smooth as
                  possible for you. We offer white glove service, with full
                  clean out service, along with packing and moving assistance.
                </p>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
        <v-row align="center" justify="center">
          <v-btn outlined dark x-large class="font-weight-light mt-10">
            Get My Cash Offer Today
            <v-icon dark right> mdi-greater-than </v-icon>
          </v-btn>
        </v-row>
      </v-col>
    </v-card>
  </v-row>
</template>

<script>
import basicConfiguration from "../../basicConfiguration.json"

export default {
  data: () => ({
    point1Text: "",
    point1description: "",
    point1icon: "",

    point2Text: "",
    point2description: "",
    point2icon: "",

    point3Text: "",
    point3description: "",
    point3icon: "",

    point4Text: "",
    point4description: "",
    point4icon: "",
  }),
  mounted() {
    this.point1icon = basicConfiguration.point1icon
    this.point1text = basicConfiguration.point1text
    this.point1description = basicConfiguration.point1description

    this.point2icon = basicConfiguration.point2icon
    this.point2text = basicConfiguration.point2text
    this.point2description = basicConfiguration.point2description

    this.point3icon = basicConfiguration.point3icon
    this.point3text = basicConfiguration.point3text
    this.point3description = basicConfiguration.point3description

    this.point4icon = basicConfiguration.point4icon
    this.point4text = basicConfiguration.point4text
    this.point4description = basicConfiguration.point4description

    this.whatmakesusdifferentButtonText = basicConfiguration.whatmakesusdifferentButtonText

  }
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=Open+Sans:400,600");
hr {
  height: 0;
  margin: 0;
  padding: 0;
  border: 0;
}

.style14 {
  text-align: center;
  border-top: 2px dashed white;
  width: 250px;
}

.style14::after {
  font: normal normal;
}
</style>
