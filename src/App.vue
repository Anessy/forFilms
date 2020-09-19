<template>
    <v-app>
        <AppBar/>

        <v-main>
            <Find @filmWord='selectFilms'/>
            <Cards />
            <Films :word='word'/>
            <HelloWorld/>
        </v-main>
    </v-app>
</template>

<script>
    import HelloWorld from './components/HelloWorld';
    import AppBar from './components/AppBar';
    import Films from './components/Films';
    import Find from './components/AutocomleteComponent'
    import Cards from './components/Cards';


    export default {
        name: 'App',
        components: {
            AppBar,
            HelloWorld,
            Films,
            Find,
            Cards
        },

        methods: {
            selectFilms(word){
                return word
            }
        },

        data () {
            return {
                word: this.methods.selectFilms,
            }
        },
    };
</script>
