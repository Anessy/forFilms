<template>
    <div>
            <v-card
                    dark
                    color="darkgrey"
            >
                <v-autocomplete
                        v-model="select"
                        :loading="loading"
                        :items="items"
                        :search-input.sync="search"
                        cache-items
                        class="mx-4"
                        flat
                        hide-no-data
                        hide-details
                        label="word in the title"
                        solo-inverted
                ></v-autocomplete>

                <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn v-on:click="filmWord()">
                        Choose
                    </v-btn>
                </v-card-actions>

            </v-card>
    </div>
</template>

<script>
    import Vuetify from 'vuetify';
    export default {
        vuetify: new Vuetify(),
        data () {
            return {
                word: null,
                loading: false,
                items: [],
                search: null,
                select: null,
                states: [
                    'love',
                    'crazy',
                    'stupid',
                    'stop',
                    'bomb',
                    'learn',
                    'actually',
                    'you',
                    'drugs',
                    'punch',
                    'mood',
                    'rosie',
                    'hate',
                    'want',
                    'Hawaii',
                    'Idaho',
                    'Illinois',
                    'Indiana',
                    'Iowa',
                    'Kansas',
                    'Kentucky',
                    'Louisiana',
                    'Maine',
                    'Marshall Islands',
                    'Maryland',
                    'Massachusetts',
                    'Michigan',
                    'Minnesota',
                    'Mississippi',
                    'Missouri',
                    'Montana',
                    'Nebraska',
                    'Nevada',
                    'New Hampshire',
                    'New Jersey',
                    'New Mexico',
                    'New York',
                    'North Carolina',
                    'North Dakota',
                    'Northern Mariana Islands',
                    'Ohio',
                    'Oklahoma',
                    'Oregon',
                    'Palau',
                    'Pennsylvania',
                    'Puerto Rico',
                    'Rhode Island',
                    'South Carolina',
                    'South Dakota',
                    'Tennessee',
                    'Texas',
                    'Utah',
                    'Vermont',
                    'Virgin Island',
                    'Virginia',
                    'Washington',
                    'West Virginia',
                    'Wisconsin',
                    'Wyoming',
                ],
            }
        },
        watch: {
            search (val) {
                val && val !== this.select && this.querySelections(val)
                if (val == this.select ) {
                   this.word = val;
                }

            },
        },
        methods: {
            querySelections (v) {
                this.loading = true
                // Simulated ajax query
                setTimeout(() => {
                    this.items = this.states.filter(e => {
                        return (e || '').toLowerCase().indexOf((v || '').toLowerCase()) > -1
                    })
                    this.loading = false
                }, 500)
            },
            filmWord () {
                this.$emit('filmWord', this.word);
            }
        },
    }
</script>

<style scoped>

</style>