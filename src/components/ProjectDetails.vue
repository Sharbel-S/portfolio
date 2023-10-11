<template>
    <div>
        <v-dialog persistent transition="dialog-top-transition" scrollable max-width="1400">
            <template v-slot:activator="{ on, attrs }">
                <v-btn class="white--text" depressed color="#3753bd" v-bind="attrs" v-on="on">More Details</v-btn>
            </template>
            <template v-slot:default="dialog">
                <v-card color="#313342">
                    <v-toolbar class="cent" color="#3753bd" dark>
                        <div>
                            <h2 class="fontColor"> {{ data.title }}</h2>
                        </div>
                    </v-toolbar>

                    <v-card-text class="backgroundColor">
                        <br>
                        <v-row>

                            <v-col cols="12" :md="getSize(data.details.photos) == 0 ? 0 : 5">
                                <b class="fontColor textSizeTitle">
                                    <v-icon dense color="#3753bd">
                                        mdi-account-multiple
                                    </v-icon> Team:
                                </b> <br>
                                <p style="display:inline" class="fontColor textSizeDescription"> {{ data.details.team }}
                                </p>
                                <br><br> <br>
                                <p style="display:inline" class="fontColor textSizeTitle">
                                    <v-icon dense color="#3753bd">
                                        mdi-calendar-blank
                                    </v-icon> Year:
                                </p>
                                <p class="fontColor textSizeDescription"> {{ data.year }} </p>

                                <br>
                                <b class="fontColor textSizeTitle">
                                    <v-icon dense color="#3753bd">
                                        mdi-domain
                                    </v-icon> Technologies:

                                </b> <br> <b class="fontColor textSizeSousTitle">Front-End: </b>
                                <p style="display:inline" class="fontColor textSizeDescription">{{
                                        data.details.technologies.frontEnd
                                }} </p> <br>
                                <b class="fontColor textSizeSousTitle ">Back-end:</b>
                                <p style="display:inline" class="fontColor textSizeDescription"> {{
                                        data.details.technologies.backEnd
                                }}</p> <br> <br> <br>

                                <b class="fontColor textSizeTitle">
                                    <v-icon dense color="#3753bd">
                                        mdi-message-text
                                    </v-icon> Description:
                                </b>
                                <p class="fontColor textSizeDescription">
                                <ul>
                                    <li v-for="(i) in data.details.description" :key="i">
                                        {{ i }}
                                    </li>
                                </ul>

                                </p> <br>

                                <b class="fontColor textSizeTitle">
                                    <v-icon dense color="#3753bd">
                                        mdi-arrow-up-bold-box-outline
                                    </v-icon> Live Demo:
                                </b> <a :href="data.details.liveDemo" target="_blank"
                                    class="fontColor textSizeDescription">
                                    {{ data.details.liveDemo }} </a>


                            </v-col>
                            <v-col cols="12" md="7">
                                <v-carousel cycle height="auto" hide-delimiters show-arrows-on-hover>
                                    <v-carousel-item v-for="(item, i) in data.details.photos" :key="i">
                                        <v-img :src="getImgUrl(item)" contain height="500"></v-img>
                                    </v-carousel-item>
                                </v-carousel>
                            </v-col>
                        </v-row>


                    </v-card-text>
                    <v-divider class="mx-2" color="#ffffff"></v-divider>

                    <v-card-actions class="justify-end backgroundColor" src="../assets/">
                        <v-btn class="white--text" depressed color="#3753bd" @click="dialog.value = false">Close</v-btn>
                    </v-card-actions>
                </v-card>
            </template>
        </v-dialog>
    </div>
</template>

<script>
export default {

    data() {
        return {
            test: true
        }
    },
    props: ['data'],

    methods: {
        getImgUrl: function (msg) {
            var images = require.context('../assets/', false, /\.png$/)
            return images('./' + msg + ".png")
        },
        getSize(photoList) {
            return photoList.length;
        }
    }
}

</script>



<style>
.cent {
    display: flex;
    justify-content: center;
    align-items: center;

}

.item>img,
.carousel-inner>.item>a>img {
    display: block;
    height: auto;
    max-width: 100%;
    line-height: 1;
    width: 100%;
}

.textSizeTitle {
    font-size: 20px;
}

.textSizeSousTitle {
    font-size: 17px;

}

.textSizeDescription {
    font-size: 17px;
}
</style>