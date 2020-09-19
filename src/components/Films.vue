<template class="allCards">
    <div>
        <div>
{{word}}

            <div >
                <v-card
                        class="mx-auto"
                        max-width="90%"
                >
                    <v-container fluid>
                        <v-row dense>
                            <v-col v-for="(course, index) in courses" :key="index"
                                    :cols="4" >
                                <v-card height="600" max-width="300">
                <img :src="course.Poster" style="width: 100%">
                <p class="title"> {{course.Title}} </p>
                <p>Year: {{course.Year}}</p>
                <p>ID: {{course.imdbID}}</p>
                                </v-card>
                            </v-col>
                        </v-row>
                    </v-container>
                </v-card>
            </div>

        </div>
    </div>
</template>

<script>
    import axios from 'axios';
    import Vuetify from 'vuetify';

    export default {
        vuetify: new Vuetify(),
        data() {
            return {
                courses: null
            }
        },
        props: ['word'],
        mounted() {
            axios
                .get('http://www.omdbapi.com/?apikey=e9a2816f&s="Love"')
                .then(response => this.courses = response.data.Search)
        }
    }
</script>


<style scoped>


</style>
