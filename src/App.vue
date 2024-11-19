<script>
import AppExercises from './components/AppExercises.vue';
import AppHeader from './components/AppHeader.vue';

export default {
    data() {
        return {

        }
    },
    components: {
      AppExercises,
      AppHeader,
    }
}
</script>

<template>
  <AppHeader/>
  <AppExercises />
</template>

<style lang="scss">
  @use "bootstrap/scss/bootstrap.scss" as *;
  @use "./assets/styles/general.scss" as *;
</style>
