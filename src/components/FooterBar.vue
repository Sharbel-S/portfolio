<template>
  <div>
    <v-footer absolute dark padless>
      <v-card class="flex" flat tile color="#3753bd">
        <v-card-text class="py-2 white--text text-center">
          <h3 class="updateDate fontColor"> Last updated on 12-29-2022 </h3>
          <h5 class="creation fontColor"> Created by © Sharbel SEKIAS 
          </h5>
        </v-card-text>
      </v-card>
    </v-footer>
  </div>
</template>

<script>
export default {
  data: () => ({
  }),
}
</script>


<style>
.updateDate {
  font-size: medium !important;

}

.creation {
  font-size: x-small;

}

.monospace {
  /* font-family: "Courier New", Courier, monospace; */
  font-size: x-large;
  color: rgb(255, 255, 255);
}
</style>