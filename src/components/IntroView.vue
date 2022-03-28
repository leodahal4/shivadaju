<template>
  <v-container
    fluid
  >
    <v-row
      class="text-center"
      dense
      fill-height
    >
      <v-col cols="6" md="12" sm="12" xs="12" lg="6" xl="6">
        <v-card class="pa-5 fill-height" elevation="12" rounded>
          <v-card-title class="text-h4 text-capitalize ml-10 text-center">
            <v-row align="center" justify="center">
              <v-col cols="12" md="12" sm="12">
                Welcome to <b class="primary--text">Demo Ecommerce</b><br/>
                Work with the best!
              </v-col>
            </v-row>
          </v-card-title>
          <hr class="style2">
          <v-card-text class="font-weight-light text-h6 text-justify">
            <div class="ml-10">
              Lorem, ipsum dolor sit amet consectetur adipisicing elit. Pariatur dolores eaque impedit neque earum veritatis autem ipsam, quisquam excepturi voluptatibus, facere obcaecati quo? Perferendis hic, cum voluptates quia nisi ullam?<br/>
              Lorem, ipsum dolor sit amet consectetur adipisicing elit. Pariatur dolores eaque impedit neque earum veritatis autem ipsam, quisquam excepturi voluptatibus, facere obcaecati quo? Perferendis hic, cum voluptates quia nisi ullam?<br/>
              Lorem, ipsum dolor sit amet consectetur adipisicing elit. Pariatur dolores eaque impedit neque earum veritatis autem ipsam, quisquam excepturi voluptatibus, facere obcaecati quo? Perferendis hic, cum voluptates quia nisi ullam?<br/>
            </div>
          </v-card-text>
        </v-card>
      </v-col>

      <v-col cols="6" sm="12" md="12" xs="12" lg="6" xl="6">
        <v-card elevation="12">
          <v-img
            lazy-src="../assets/into.jpg"
            src="../assets/into.jpg"
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
</template>

<script>
export default {
created() {
        switch (this.$vuetify.breakpoint.name) {
          case 'xs': console.log(220)
          case 'sm': console.log(400)
          case 'md': console.log(500)
          case 'lg': console.log(600)
          case 'xl': console.log(800)
        }
    }
}
</script>

<style>

hr.style2 { 
  height: 30px; 
  border-style: solid; 
  border-color: #8c8b8b; 
  border-width: 1px 0 0 0; 
  border-radius: 20px; 
  margin-left: 30%;
  width: 400px;
} 
hr.style2:before { 
  display: block; 
  content: ""; 
  height: 30px; 
  margin-top: -31px; 
  border-style: solid; 
  border-color: #8c8b8b; 
  border-width: 0 0 1px 0; 
  border-radius: 20px; 
}

</style>
