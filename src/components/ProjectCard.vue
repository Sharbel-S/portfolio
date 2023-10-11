<template>
    <div>
        <v-card class="mx-auto my-3" max-width="374" color="#0f2e4c">
            <template slot="progress">
                <v-progress-linear color="deep-purple" height="10" indeterminate></v-progress-linear>
            </template>
            <v-img height="250" :src="getImgUrl(data.photoLink)"></v-img>
            <v-card-title>
                <h4 class="fontColor"> {{ data.title }} </h4>
            </v-card-title>
            <v-card-text>
                <v-row align="center" class="mx-0">
                    <v-icon dense color="#ffffff">
                        mdi-calendar-blank
                    </v-icon>
                    &nbsp;
                    <div class="fontColor">
                        {{ data.year }}
                    </div>
                </v-row>

                <div class="my-4 text-subtitle-1 ">
                </div> <br>
                <v-divider class="mx-2"></v-divider>

                <br>
                <div class="fontColor cardDesc">{{ data.description }}
                </div>
            </v-card-text>
            <v-card-actions class="red--text">
                <PacmaniaDetails :data="data" />
            </v-card-actions>
        </v-card>
    </div>
</template>

<script>
import PacmaniaDetails from './ProjectDetails.vue';


export default {

    components: { PacmaniaDetails },
    props: ['data'],

    methods: {
        getImgUrl: function (msg) {
            var images = require.context('../assets/', false, /\.png$/)
            return images('./' + msg + ".png")
        }
    }
}
</script>


<style>
.cardDesc {
    font-size: 15px;
}

.theme--light.v-divider {
    border-color: #3753bd !important;
}
</style>