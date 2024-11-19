<script>
import AppMain from './components/AppMain.vue';
import AppHeader from './components/AppHeader.vue';

export default {
    data() {
        return {

        }
    },
    components: {
      AppMain,
      AppHeader,
    }
}
</script>

<template>
  <AppHeader/>
  <AppMain />
</template>

<style lang="scss">
  @use "bootstrap/scss/bootstrap.scss" as *;
  @use "./assets/styles/general.scss" as *;
</style>
