<template> 
  <div>
    <AppBar />
    <HomePicture />
    <v-row align="center" justify="center" class="mt-7">
      <hr class="defaultHr"/>
    </v-row>
    <IntroView/>
    <v-row align="center" justify="center" class="mt-7">
      <hr class="defaultHr"/>
    </v-row>
    <WhatMakesUsDifferent/>
    <v-row align="center" justify="center" class="mt-7">
      <hr class="defaultHr"/>
    </v-row>
    <InstantQuote/>
    <FooterView/>
  </div>
</template>

<script>
import AppBar from '../components/AppBar';
import HomePicture from '../components/HomePicture';
import WhatMakesUsDifferent from '../components/WhatMakesUsDifferent';
import IntroView from '../components/IntroView';
import InstantQuote from '../components/InstantQuote';
import FooterView from '../components/FooterView';

export default {
  name: "Home",

  components: {
    AppBar,
    InstantQuote,
    HomePicture,
    FooterView,
    IntroView,
    WhatMakesUsDifferent
  },
};
</script>
<style>
hr.defaultHr { 
  height: 30px; 
  border-style: solid; 
  border-color: #8c8b8b; 
  border-width: 1px 0 0 0; 
  border-radius: 20px; 
  width: 96%;
} 
hr.defaultHr:before { 
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
