<template>
  <div>
    <v-app class="backgroundColor font">
      <HeaderBar />
      <FooterBar />
    </v-app>
  </div>


</template>
<script>
//import testTo from './components/TestTo.vue';
import HeaderBar from './components/HeaderBar.vue'
import FooterBar from './components/FooterBar.vue'

export default {
  components: { HeaderBar, FooterBar },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Raleway:wght@500&display=swap');
.backgroundColor {
  background-color: #0C243C !important;
}

.sectionsColor {
  color: #3753bd !important;
}

.fontColor {
  color: rgb(255, 255, 255);

}

.font {
  font-family: 'Raleway', sans-serif;
  color: rgb(255, 255, 255) !important;
}


</style>