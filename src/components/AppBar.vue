<template>
  <v-app-bar
    max-width="100vw"
    max-height="75"
    :color="appBarcolor"
    app
    v-scroll="changeColorOnScroll"
    elevate-on-scroll
    :dark="dark"
    height="70"
  >
    <v-toolbar-title>
      <v-btn
        text
        rounded
        to="/"
        color="transparent"
        height="70"
        v-if="checkMobileDesktop"
      >
        <v-img
          lazy-src="../assets/demologo.png"
          src="../assets/demologo.png"
          contain
          width="110"
          height="70"
          class="mr-5"
        >
          <template v-slot:placeholder>
            <v-row class="fill-height ma-0" align="center" justify="center">
              <v-progress-circular
                indeterminate
                color="primary"
              ></v-progress-circular>
            </v-row>
          </template>
        </v-img>
        <div :class="appBarContentColor">Ecommerce</div>
      </v-btn>
      <v-btn
        text
        rounded
        to="/"
        color="transparent"
        height="70"
        v-else
        class="mr-10"
      >
        <v-img
          src="../assets/demologo.png"
          contain
          width="70"
          height="30"
          class="mr-5"
        />
        <div :class="appBarContentColor">Ecommerce</div>
      </v-btn>
    </v-toolbar-title>
    <v-spacer />
    <div id="nav" v-if="checkMobileDesktop">
      <v-btn
        text
        rounded
        v-for="link in routes"
        :key="link.name"
        :to="link.link"
        small
      >
        <div :class="appBarContentColor">
          {{ link.name }}
        </div>
      </v-btn>
    </div>
    <v-spacer v-if="checkMobileDesktop" />
    <div class="hidden-xs-and-down mr-5" v-if="checkMobileDesktop">
      <v-menu offset-y>
        <template v-slot:activator="{ attrs, on }">
          <v-btn text rounded v-bind="attrs" v-on="on">
            <v-icon> mdi-account </v-icon>
            Account
          </v-btn>
        </template>
        <v-list>
          <v-dialog v-model="loginDialog" persistent max-width="400px">
            <template v-slot:activator="{ on, attrs }">
              <v-list-item>
                <v-list-item-title v-bind="attrs" v-on="on">
                  Login
                </v-list-item-title>
              </v-list-item>
            </template>
            <LoginCard @closeLoginDialog="loginDialog = false" />
          </v-dialog>
          <v-dialog v-model="registerDialog" persistent max-width="600px">
            <template v-slot:activator="{ on, attrs }">
              <v-list-item>
                <v-list-item-title v-bind="attrs" v-on="on">
                  Register
                </v-list-item-title>
              </v-list-item>
            </template>
            <RegisterCard @closeRegisterDialog="registerDialog = false" />
          </v-dialog>
        </v-list>
      </v-menu>
    </div>
    <v-dialog
      v-else
      v-model="appNavDialog"
      fullscreen
      hide-overlay
      transition="dialog-bottom-transition"
    >
      <template v-slot:activator="{ on, attrs }">
        <v-app-bar-nav-icon
          :class="appBarContentColor"
          dark
          v-bind="attrs"
          v-on="on"
        />
      </template>
      <v-card>
        <v-toolbar dark color="primary">
          <v-toolbar-title>
            <v-btn
              text
              rounded
              to="/"
              color="transparent"
              height="70"
              class="mr-10"
            >
              <v-img
                src="../assets/demologo.png"
                contain
                width="70"
                height="30"
              />
              <div class="white--text">Ecommerce</div>
            </v-btn>
          </v-toolbar-title>
          <v-spacer />
          <v-toolbar-items>
            <v-btn icon dark @click="appNavDialog = false">
              <v-icon>mdi-close</v-icon>
            </v-btn>
          </v-toolbar-items>
        </v-toolbar>
        <v-list two-line dense>
          <v-list-item
            v-for="(links, index) in mobileRoutes"
            :key="index"
            link
            :to="links.link"
            dense
          >
            <v-list-item-content>
              <v-list-item-title v-text="links.name" />
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-card>
    </v-dialog>
  </v-app-bar>
</template>

<script>
import LoginCard from "./LoginCard";
import RegisterCard from "./RegisterCard";

export default {
  name: "AppBar",
  components: {
    LoginCard,
    RegisterCard,
  },
  data() {
    return {
      appNavDialog: false,
      routes: [
        { name: "Vision", link: "/vision" },
        { name: "How It Works", link: "/how-it-works" },
        { name: "About", link: "/about" },
        { name: "Categories", link: "/categories" },
        { name: "Custom", link: "/custom" },
      ],
      mobileRoutes: [
        { name: "Vision", link: "/vision" },
        { name: "About", link: "/about" },
        { name: "Categories", link: "/categories" },
        { name: "Login", link: "/login" },
        { name: "Custom", link: "/custom" },
        { name: "Register", link: "/register" },
      ],
      appBarcolor: "transparent",
      dark: false,
      appBarContentColor: "blue--text",
      loginDialog: false,
      registerDialog: false,
    };
  },
  methods: {
    searchButton() {},
    changeColorOnScroll(e) {
      if (typeof window === "undefined") return;
      const top = window.pageYOffset || e.target.scrollTop || 0;
      if (top > 20) {
        this.appBarcolor = "primary";
        this.appBarContentColor = "white--text";
        this.dark = true;
      } else {
        this.appBarcolor = "transparent";
        this.appBarContentColor = "blue--text";
        this.dark = false;
      }
    },
  },
  computed: {
    checkMobileDesktop() {
      if (
        this.$vuetify.breakpoint.name === "xs" ||
        this.$vuetify.breakpoint.name === "sm"
      ) {
        return false;
      }
      return true;
    },
  },
};
</script>

<style scoped>
.v-chip:hover {
  cursor: pointer;
}
</style>
