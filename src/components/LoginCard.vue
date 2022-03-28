<template>
  <v-card
    width="400"
    opacity="10"
  >
    <v-card-title>
      <span class="headline">User Profile</span>
    </v-card-title>
    <v-card-text>
      <v-container>
        <v-row>
          <v-col cols="12">
            <v-text-field
              label="Email*"
              required
            />
          </v-col>
          <v-col cols="12">
            <v-text-field
              label="Password*"
              type="password"
              required
            />
          </v-col>
        </v-row>
      </v-container>
      <small>*indicates required field</small>
    </v-card-text>
    <v-card-actions>
      <v-spacer />
      <v-btn
        color="blue darken-1"
        text
        @click="closeLoginDialog()"
      >
        Close
      </v-btn>
      <v-btn
        color="blue darken-1"
        text
        @click="closeLoginDialog()"
      >
        Login
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  methods: {
    closeLoginDialog () {
      this.$emit('closeLoginDialog')
    }
  }

}
</script>

<style>

</style>
