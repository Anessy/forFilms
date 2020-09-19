<template class="allCards">
    <div>
        <div>
            
            <div class="card" v-for="(course, index) in courses" :key="index">
                <img :src="course.Poster" style="width: 100%">
                <p class="title"> {{course.Title}} </p>
                <p>Year: {{course.Year}}</p>
                <p>ID: {{course.imdbID}}</p>
            </div>
        </div>
    </div>
</template>

<script>
    import axios from 'axios';


    export default {
        data() {
            return {
                courses: null
            }
        },
        props: 'word',
        mounted() {
            axios
                .get('http://www.omdbapi.com/?apikey=e9a2816f&s="Love"')
                .then(response => this.courses = response.data.Search)
        }
    }
</script>


<style scoped>
    .allCards {
        padding: 20px;
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
    }

    .card {
        box-shadow: 1px 1px 1px black;
        width: 25%;
        border: 1px black;
        margin: 10px;
    }

</style>
