<script>
import axios from 'axios';

export default {
    name: "AppMain",
    data() {
        return {
            exerciseList : [],
        }
    },
    methods: {
        getExercises() {
            axios.get('http://127.0.0.1:8000/api/exercises')
            .then((response) => {
                console.log(response.data.results);
                this.exerciseList = response.data.results;
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
        <div class="container">

        </div>
    </main>
</template>

<style lang="scss" scoped>

</style>