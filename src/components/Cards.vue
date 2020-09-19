<template>
            <v-app id="inspire">
                <v-card
                        class="mx-auto"
                        max-width="90%"
                >

                    <v-container fluid>
                        <v-row dense>
                            <v-col
                                    v-for="card in cards"
                                    :key="card.title"
                                    :cols="card.flex"
                            >
                                <v-card>
                                    <v-img
                                            :src="card.src"
                                            class="white--text align-end"
                                            gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                                            height="400px"
                                    >
                                        <v-card-title v-text="card.title"></v-card-title>
                                    </v-img>
                                    <v-card-title v-text="card.year"></v-card-title>
                                    <v-card-actions>
                                        <v-spacer></v-spacer>

                                        <v-btn icon>
                                            <v-icon>mdi-heart</v-icon>
                                        </v-btn>

                                        <v-btn icon>
                                            <v-icon>mdi-bookmark</v-icon>
                                        </v-btn>

                                        <v-btn icon>
                                            <v-icon>mdi-share-variant</v-icon>
                                        </v-btn>
                                    </v-card-actions>
                                </v-card>
                            </v-col>
                        </v-row>
                    </v-container>
                </v-card>
            </v-app>
</template>

<script>
    import Vuetify from 'vuetify';

    export default {
        vuetify: new Vuetify(),
        data() {
            return {
                cards: [
                    {
                        title: 'Pre-fab homes',
                        year: '2020',
                        src: 'https://cdn.vuetifyjs.com/images/cards/house.jpg',
                        flex: 4
                    },
                    {
                        title: 'Favorite road trips',
                        year: '2020',
                        src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg',
                        flex: 4
                    },
                    {
                        title: 'Best airlines',
                        year: '2020',
                        src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg',
                        flex: 4
                    },
                ],
            }
        }
    }
</script>

<style scoped>

</style>