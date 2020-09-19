<template>
    <v-app>
        <AppBar/>

        <v-main>
            <Find @filmWord='selectFilms'/>
            <Films word="word"/>
            <HelloWorld/>
        </v-main>
    </v-app>
</template>

<script>
    import HelloWorld from './components/HelloWorld';
    import AppBar from './components/AppBar';
    import Films from './components/Films';
    import Find from './components/AutocomleteComponent'

    export default {
        name: 'App',
        components: {
            AppBar,
            HelloWorld,
            Films,
            Find
        },

        methods: {
            selectFilms(word){
                return word
            }
        },

        data: () => ({
            //
        }),
    };
</script>
