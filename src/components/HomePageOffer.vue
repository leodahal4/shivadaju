<template>
  <v-dialog v-model="ok" max-width="35%">
    <v-card opacity="10">
      <v-card-text>
        <v-container no-gutters>
          <v-row>
            <v-col cols="6">
              <div
                align="center"
                justify="center"
                class="text-h5 font-weight-light"
              >
                You're Just
              </div>
              <div
                align="center"
                justify="center"
                class="primary--text text-h4 font-weight-light"
              >
                10 minutes Away
              </div>
              <div
                align="center"
                justify="center"
                class="text-h6 font-weight-light"
              >
                from a fair offer on your home
              </div>
              <v-text-field
                label="Enter your street address"
                placeholder="Enter your street address"
                outlined
                class="mt-5 font-weight-light"
              />
              <v-btn outlined color="primary" class="font-weight-light">
                Get an offer now.
              </v-btn>
            </v-col>
            <v-col cols="6">
              <v-card elevation="6" height="100%" width="100%">
                <v-img
                  src="../assets/offer.jpg"
                  lazy-src="../assets/offer.jpg"
                  height="100%"
                  elevation="12"
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
                </v-img>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
        <small class="red--text ml-4">*offer is only applicable once</small>
      </v-card-text>
      <v-card-actions>
        <v-spacer />
        <v-btn
          color="primary"
          @click="closeOfferDialog()"
          class="font-weight-light mb-2"
          outlined
        >
          Close
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  data: () => ({
    ok: true,
  }),
  methods: {
    closeOfferDialog() {
      this.$emit("closeOfferDialog");
    },
  },
};
</script>
