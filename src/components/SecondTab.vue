<template>

    <v-container>
        <div class="cards">


            <v-card class="mx-auto my-3" max-width="350" color="#0f2e4c">

                <template slot="progress">

                    <v-progress-linear color="deep-purple" height="10" indeterminate></v-progress-linear>
                </template>


                <v-img height="250" 
                    src="https://media.istockphoto.com/id/1332167985/photo/coming-soon-neon-sign-the-banner-shining-light-signboard-collection.jpg?b=1&s=170667a&w=0&k=20&c=Le4B-lJt-jXjeAOdlTQptNvN_DmRwWF19ShNc5VY4a4="></v-img>

                <v-card-title>
                    <h4 class="fontColor"> Rating Web app
                    </h4>

                </v-card-title>
                <v-card-text>
                    <v-row align="center" class="mx-0">
                        <v-icon dense color="#ffffff">
                            mdi-calendar-blank
                        </v-icon>
                        &nbsp;
                        <div class="fontColor">
                            2022-2023
                        </div>
                    </v-row>

                    <div class="my-4 text-subtitle-1 ">
                    </div> <br>
                    <v-divider class="mx-2"></v-divider>

                    <br>
                    <div class="fontColor cardDesc"> We are currently working on a full-stack web application using
                        Angular, Java, Hibernate, Spring-boot and PostgreSQL <br>
                        Details will be available soon 
                    </div>
                </v-card-text>
            </v-card>


            <div v-for="project in jsonFile" :key="project.title">
                <ProjectCard class="card" :data=project />
            </div>

        </div>
        <br> <br> <br> <br> <br>
    </v-container>

</template>

<script>

import ProjectCard from "./ProjectCard.vue"
import json from '../../data/data.json'

export default {
    data() {
        return {
            jsonFile: json
        }
    },
    props: {
        myJson: String,
    },
    components: { ProjectCard, },
}

</script>

<style lang="scss" scoped>
.cards {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
    grid-auto-rows: auto;
    grid-gap: 1rem;
}

.card {
    border-radius: 4px;
    padding: .5rem;
}
</style>