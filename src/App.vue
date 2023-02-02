<template>
  <div>
    <NavbarComponent />
    <home-component />
  </div>
</template>

<script>
import HomeComponent from './components/HomeComponent.vue'
import NavbarComponent from './components/NavbarComponent.vue';

export default {
  name: 'App',
  components: {
    HomeComponent,
    NavbarComponent
}
}
</script>

<style>

</style>
