<template>
  <div>
    <NavbarComponent />
    <HerooneComponent />
    <HeroDescription />
  </div>
</template>

<script>
import HeroDescription from "./components/HeroDescription.vue";
import HerooneComponent from "./components/HerooneComponent.vue";
import NavbarComponent from "./components/NavbarComponent.vue";

export default {
  name: "App",
  components: {
    NavbarComponent,
    HerooneComponent,
    HeroDescription,
  },
};
</script>

<style>
</style>
