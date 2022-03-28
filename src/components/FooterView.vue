<template>
  <v-footer absolute app color="primary darken-1 text-center" dark class="mb-0">
    <v-container fill-height fluid>
      <v-row align="center" justify="center">
        <v-col cols="12" md="3" lg="3" sm="6">
          <div class="grey--text ml-10">
            <b class="text-h6 white--text mt-0"> About </b>
            <div class="mt-3">
              Lorem ipsum dolor sit amet, Lorem ipsum dolor sit amet, Lorem
              ipsum dolor sit amet, Lorem ipsum dolor sit amet, Lorem ipsum
              dolor sit amet, Lorem ipsum dolor sit amet, Lorem ipsum dolor sit
              amet,
            </div>
          </div>
        </v-col>
        <v-col cols="12" md="3" lg="3" sm="6">
          <b class="text-h6" style="margin-bottom: 5px !important">
            Quick Links
          </b>
          <div class="mt-3">
            <div v-for="(link, index) in quickLinks" :key="index">
              <v-btn
                color="white"
                text
                rounded
                class="text-capitalize"
                :to="link.link"
              >
                {{ link.name }}
              </v-btn>
            </div>
          </div>
        </v-col>
        <v-col cols="12" md="3" lg="3" sm="6">
          <b class="text-h6">Other Links</b>
          <div class="mt-3">
            <div v-for="(link, index) in otherLinks" :key="index">
              <v-btn
                color="white"
                text
                rounded
                class="my-1 text-capitalize"
                :to="link.link"
              >
                {{ link.name }}
              </v-btn>
            </div>
          </div>
        </v-col>
        <v-col cols="12" md="3" lg="3" sm="6">
          <v-text-field
            label="Subcribe to Newsletters"
            single-line
            outlined
            @click="subscribeClicked"
            @keydown="subscribeClicked"
          />
        </v-col>
      </v-row>
      <v-row class="my-2">
        <v-divider />
      </v-row>
      <v-row
        align="center"
        justify="center"
        no-gutters
        style="margin: 0px !important"
      >
        <v-col cols="9">
          Demo Ecommerce Copyright © {{ new Date().getFullYear() }} - All rights
          reserved || Designed By: <strong>Demo Company Name</strong>
        </v-col>
        <v-col cols="3">
          <v-btn class="ma-2" outlined color="white" fab small dark>
            <v-icon>mdi-facebook</v-icon>
          </v-btn>
          <v-btn class="ma-2" outlined color="white" fab small dark>
            <v-icon>mdi-instagram</v-icon>
          </v-btn>
          <v-btn class="ma-2" outlined color="white" fab small dark>
            <v-icon>mdi-twitter</v-icon>
          </v-btn>
        </v-col>
      </v-row>
    </v-container>
    <div class="text-center">
      <v-dialog v-model="subscribeModel" width="500">
        <v-card elevation="16">
          <v-card-title class="headline primary white--text">
            Privacy Policy
          </v-card-title>
          <v-card-text style="font-size: 16px">
            <v-row class="mt-2">
              <strong>
                At first, your privacy will be secured, as we won't sell your
                Email to someone else for marketing.
              </strong>
            </v-row>
            <v-row class="mt-5">
              By subscribing to our news letter you will be notified to any
              <ul>
                <li>New Offers</li>
                <li>News</li>
                <li>And More.</li>
              </ul>
            </v-row>
          </v-card-text>
          <v-divider class="my-2" />
          <v-card-actions>
            <v-text-field
              append-icon="mdi-send"
              clear-icon="mdi-close-circle"
              clearable
              label="Enter Email address"
              type="text"
              v-model="email"
              @click:append="sendClicked"
              outlined
            />
          </v-card-actions>
        </v-card>
      </v-dialog>
    </div>
  </v-footer>
</template>

<script>
export default {
  data: () => ({
    email: "",
    quickLinks: [
      {
        name: "About Us",
        link: "/about",
      },
      {
        name: "Team",
        link: "/team",
      },
      {
        name: "Services",
        link: "/services",
      },
      {
        name: "Blog",
        link: "/blog",
      },
      {
        name: "Contact Us",
        link: "/contact",
      },
    ],
    otherLinks: [
      {
        name: "Terms & Conditions",
        link: "/terms-and-conditions",
      },
      {
        name: "Privacy Policy",
        link: "/privacy",
      },
      {
        name: "Cookie Policy",
        link: "/cookiepolicy",
      },
      {
        name: "Tickets",
        link: "/tickets",
      },
    ],
    subscribeModel: false,
  }),
  methods: {
    subscribeClicked() {
      this.subscribeModel = true;
    },
    sendClicked() {
      console.log("over here");
    },
  },
};
</script>

<style></style>
