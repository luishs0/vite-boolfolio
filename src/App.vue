<script>
import AppMain from './components/AppMain.vue';

export default {
  name: 'App',
  components: {
    AppMain
  }
}
</script>


<template>

  <main>
    <div class="container">
      <AppMain />
    </div>
  </main>

</template>


<style lang="scss">
@use "./styles/general.scss" as *;
</style>
