<script>
import axios from 'axios';

export default {
    name: "AppMain",
    data() {
        return {
            exercisesList : [],
        }
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

        <h1 class="text-center p-5">Vite Boolfolio</h1>

        <div class="container mb-5">
            <div class="row row-cols-6 gap-4 justify-content-center">
                <div class="col text-center text-white" v-for="exercise in exercisesList" :key="exercise.id">
                    <p class="mt-3">
                        <span class="fw-bold">Nome Esercizio: </span>{{exercise.exercise_name}}
                    </p>

                    <p>
                        <span class="fw-bold">Nome repo: </span>{{exercise.repo_name}}
                    </p>

                    <p>
                        <span class="fw-bold">Esercizio completato: </span>{{exercise.exercise_completed}}
                    </p>

                    <p>
                        <span class="fw-bold">Bonus dell'esercizio: </span>{{exercise.exercise_bonus}}
                    </p>

                    <p>
                        <span class="fw-bold">Data: </span>{{exercise.date}}
                    </p>
                </div>
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