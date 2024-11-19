<script>

export default {
    name: "AppExercisesCards",
    data() {
        return {
        }
    },
    props: {
        exerciseObj : {
            type: Object,
            required: true,
        }
    },
}
</script>

<template>
    <div class="col text-center text-white">
        <p class="mt-3">
            <span class="fw-bold">Nome Esercizio: </span>{{exerciseObj.exercise_name}}
        </p>

        <p>
            <span class="fw-bold">Nome repo: </span>{{exerciseObj.repo_name}}
        </p>

        <p>
            <span class="fw-bold">Esercizio completato: </span>{{exerciseObj.exercise_completed}}
        </p>

        <p>
            <span class="fw-bold">Bonus dell'esercizio: </span>{{exerciseObj.exercise_bonus}}
        </p>

        <p>
            <span class="fw-bold">Data: </span>{{exerciseObj.date}}
        </p>
    </div>

</template>

<style lang="scss" scoped>
    .col {
        background-color: black;
        border-radius: 10px;
        box-shadow: 0px 5px 10px grey;
    }
</style>