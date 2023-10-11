<template>
  <div>
    <v-tabs height="50" fixed-tabs background-color="#3753bd" v-model="model" centered slider-color="yellow">
      <v-tab  class="dd white--text" href="#1"> About me
      </v-tab>
      <v-tab class="dd white--text" href="#2"> my Projects
      </v-tab>
    </v-tabs>

    <v-tabs-items v-model="model" class="backgroundColor">
      <v-tab-item value="1">
        <FirstTab />
      </v-tab-item>

      <v-tab-item value="2">
        <SecondTab />
      </v-tab-item>
    </v-tabs-items>
  </div>
</template>

<script>
import FirstTab from "./FirstTab.vue"
import SecondTab from "./SecondTab.vue"


export default {
  data() {
    return {
      model: 'tab-2',
    }
  },
  components: { FirstTab, SecondTab },
}
</script>

<style lang="scss" scoped>
.backgroundColor {
  background-color: #0C243C;
}

.dd {
  font-size: medium;
}
</style>