<template>
  <v-container fluid>
    <AppBar/>
    <v-row align="center" justify="center" style="margin-top: 100px; margin-bottom: 50px;">
        <div class="font-weight-thin text-capitalize text-h4">
          Selling
          <span class="primary--text mx-2">
            Home
          </span>
          have never been so
          <span class="primary--text">
            easy
          </span>.
        </div>
    </v-row>
    <v-row align="center" justify="center" class="text-center">
      <v-hover
        v-slot="{ hover }"
      >
      <v-card :elevation="hover? 6 : 2" :class="{ 'on-hover': hover }" class="pa-10 ma-5">
        <v-row align="center" justify="center">
          <v-col cols="5">
            <v-card elevation="10" class="px-1 pt-1">
              <iframe
                style="width: 100%; height: 580px;"
                :src="result"
                frameborder="0"
                allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
                allowfullscreen
              ></iframe>
            </v-card>
          </v-col>
          <v-col cols="5">
              <div class="font-weight-light text-h3 primary--text">
                HOW IT WORKS
              </div>
              <div class="font-weight-light text-h5 mt-10">
                We understand the challenges of selling a home. Between closing costs, agent fees, paperwork, transfer tax, moving expenses, and more – it can seem like there’s no end to the hassle. Our company cuts through the red tape and helps you sell your house fast.
              </div>
          </v-col>
        </v-row>
      </v-card>
      </v-hover>
    </v-row>
    <hr class="style2">
    <v-row align="center" justify="center" class="text-center">
      <v-hover
        v-slot="{ hover }"
      >
        <v-card style="width: 100%;" class="pa-5 ma-5" :elevation="hover ? 6 : 2"
          :class="{ 'on-hover': hover }">
          <div class="text-h2 font-weight-thin">
            With Us,
          </div>
          <div class="text-capitalize text-h5 font-weight-light mt-8">
            It's as easy as
            <span class="primary--text mx-2">
              1-2-3
            </span>
            and 
            <span class="primary--text">
              done
            </span>
            .
          </div>
          <template>
          <v-timeline :dense="$vuetify.breakpoint.smAndDown">
            <v-timeline-item
              color="purple lighten-2"
              fill-dot
              right
            >
              <v-card>
                <v-card-title class="primary">
                    <v-icon size="42" dark class="mr-4">
                     mdi-home-heart 
                    </v-icon>
                  <h2 class="text-h4 white--text font-weight-light text-uppercase">
                    Tell Us About Your Property
                  </h2>
                </v-card-title>
                <v-container>
                  <v-row>
                    <v-col
                      cols="12"
                      md="10"
                    >
                      Lorem ipsum dolor sit amet consectetur, adipisicing elit. Nihil velit ratione ullam labore qui quia quod totam fugit assumenda quas! Distinctio nihil voluptates laudantium ipsam corrupti possimus non cum officiis!
                    </v-col>
                  </v-row>
                </v-container>
              </v-card>
            </v-timeline-item>

            <v-timeline-item
              color="amber lighten-1"
              fill-dot
              left
              small
            >
              <v-card>
                <v-card-title class="primary justify-end">
                  <h2 class="text-h4 mr-4 white--text font-weight-light text-uppercase">
                     SCHEDULE AN APPOINTMENT 
                  </h2>
                  <v-icon
                    dark
                    size="42"
                  >
                   mdi-calendar-heart 
                  </v-icon>
                </v-card-title>
                <v-container>
                  <v-row>
                    <v-col
                      cols="12"
                    >
                      Lorem ipsum dolor sit amet consectetur adipisicing elit. Labore illo repellendus laborum error ipsam facere quas tempora cupiditate, blanditiis incidunt pariatur quos deleniti expedita minus vero, non suscipit nesciunt unde?
                    </v-col>
                  </v-row>
                </v-container>
              </v-card>
            </v-timeline-item>

            <v-timeline-item
              color="cyan lighten-1"
              fill-dot
              right
            >
              <v-card>
                <v-card-title class="primary">
                  <v-icon
                    class="mr-4"
                    dark
                    size="42"
                  >
                    mdi-clock
                  </v-icon>
                  <h2 class="text-h4 white--text font-weight-light">
                     We'll close fast 
                  </h2>
                </v-card-title>
                <v-container>
                  <v-row>
                    <v-col cols="12">
                      Lorem ipsum dolor sit amet consectetur adipisicing elit. Amet, quibusdam architecto officiis dolor, cumque non aspernatur similique tenetur a error, minus totam nulla? Facere, quis voluptatibus dicta nam eos magnam.
                    </v-col>
                  </v-row>
                </v-container>
              </v-card>
            </v-timeline-item>
          </v-timeline>
        </template>
        </v-card>
      </v-hover>
    </v-row>
    <hr class="style2">
    <InstantQuote/>
    <FooterView />
  </v-container>
</template>

<script>
import AppBar from '../components/AppBar';
import InstantQuote from '../components/InstantQuote.vue';
import FooterView from '../components/FooterView.vue';

export default {
  components: {
    AppBar,
    InstantQuote,
    FooterView
  },
  data: () => ({
    result: "",
    youtubeURL: "https://www.youtube.com/watch?v=1jqYDyKsWNw",
  }),
  mounted () {
      const currentCursor = this
      const youtubeEmbedTemplate = 'https://www.youtube.com/embed/'
      const url = currentCursor.youtubeURL.split(/(vi\/|v%3D|v=|\/v\/|youtu\.be\/|\/embed\/)/)
      console.log("url", url)
      const YId = undefined !== url[2] ? url[2].split(/[^0-9a-z_/\\-]/i)[0] : url[0]
      console.log("YId", YId)
      if (YId === url[0]) {
        console.log("not a youtube link")
      } else {
        console.log("it's  a youtube video")
      }
      const topOfQueue = youtubeEmbedTemplate.concat(YId)
      console.log("topOfQueue", topOfQueue)
      currentCursor.result = topOfQueue
      currentCursor.youtubeURL = ''
    }
  }

</script>

<style>

</style>
