<script>
import axios from 'axios';
import AppExercisesCards from './AppExercisesCards.vue';

export default {
    name: "AppExercises",
    data() {
        return {
            exercisesList : [],
        }
    },
    components: {
        AppExercisesCards
    },
    methods: {
        getExercises() {
            axios.get('http://127.0.0.1:8000/api/exercises')
            .then((response) => {
                console.log(response.data.results);
                this.exercisesList = response.data.results;
            })
            .catch(function (error) {
                console.log(error);
            })
        }
    },
    mounted() {
        this.getExercises();
    }
}
</script>

<template>
    <main>

        <div class="container mb-5">
            <div class="row row-cols-6 gap-4 justify-content-center">
                <AppExercisesCards v-for="exercise in exercisesList" :key="exercise.id" :exerciseObj="exercise" />
            </div>
        </div>
        
    </main>
</template>

<style lang="scss" scoped>
    .col {
        background-color: black;
        border-radius: 10px;
        box-shadow: 0px 5px 10px grey;
    }
</style>