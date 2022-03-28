<template>
  <v-container fluid style="margin-bottom: 350px">
    <v-row fill-height dense>
      <v-col cols="6">
        <v-row align="center" justify="center">
          <v-col cols="12">
            <v-card class="pa-5 text--primary" elevation="12">
              <v-card-title class="text-h3 font-weight-thin">
                Get an <span class="primary--text ml-2">Instant Quote</span>
              </v-card-title>
              <hr
                style="
                  margin-left: 20px;
                  border-top: 3px double black;
                  width: 50%;
                "
              />
              <v-card-text class="mt-4">
                <v-row dense>
                  <v-col cols="12">
                    <v-text-field
                      label="Enter your street address"
                      placeholder="Enter your street address"
                      outlined
                      class="ma-0 pa-0"
                      rounded
                    />
                  </v-col>
                </v-row>
                <v-row dense>
                  <v-col cols="6">
                    <v-text-field
                      label="Enter your Name"
                      placeholder="Enter your Name"
                      outlined
                      class="ma-0 pa-0"
                      rounded
                    />
                  </v-col>
                  <v-col cols="6">
                    <v-text-field
                      label="Enter your Phone Number"
                      placeholder="Enter your Phone Number"
                      outlined
                      class="ma-0 pa-0"
                      rounded
                    />
                  </v-col>
                </v-row>
                <v-row dense>
                  <v-col cols="12">
                    <v-text-field
                      label="Enter your Email Address"
                      placeholder="Enter your Email Address"
                      outlined
                      class="ma-0 pa-0"
                      rounded
                    />
                  </v-col>
                </v-row>
                <v-row dense>
                  <v-col cols="12"> </v-col>
                  <v-select
                    :items="items"
                    label="How Did You Find Us ?"
                    placeholder="How Did You Find Us ?"
                    solo
                    rounded
                    outlined
                    class="ma-0 pa-0"
                  ></v-select>
                </v-row>
                <v-row dense>
                  <v-col cols="12">
                    <v-checkbox v-model="checkbox">
                      <template v-slot:label>
                        <div>
                          By checking this box, I consent to receiving text
                          messages or calls with offers or information provided
                          by
                          <v-tooltip bottom>
                            <template v-slot:activator="{ on }">
                              <a
                                target="_blank"
                                href="localhost:8081/data-policy"
                                @click.stop
                                v-on="on"
                                class="primary--text"
                              >
                                Demo Ecommerce
                              </a>
                            </template>
                            Data Policy
                          </v-tooltip>
                          about this property. You can opt out at any time.
                        </div>
                      </template>
                    </v-checkbox>
                  </v-col>
                </v-row>
                <v-row align="center" justify="center">
                  <v-btn outlined x-large class="font-weight-light mt-10">
                    Get My Cash Offer Today
                    <v-icon dark right> mdi-greater-than </v-icon>
                  </v-btn>
                </v-row>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-col>
      <v-col cols="6">
        <v-card elevation="12" class="fill-height">
          <v-img src="../assets/home1.jpg" class="fill-height">
            <template v-slot:placeholder>
              <v-row class="fill-height ma-0" align="center" justify="center">
                <v-progress-circular
                  indeterminate
                  color="grey lighten-5"
                ></v-progress-circular>
              </v-row>
            </template>
          </v-img>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    items: ["Google", "Refer", "Direct Mail", "Social Media", "Other"],
  }),
};
</script>

<style></style>
