<template>
  <NavbarComponent />
  <div class="container">
    <router-view />
  </div>
</template>

<script>
import { RouterLink } from "vue-router";
import NavbarComponent from "./components/Navbar.vue";

export default {
  name: "App",
  components: {
    NavbarComponent,
  },

  props: {
    // add @ts-ignore if using TypeScript
    ...RouterLink.props,
    inactiveClass: String,
  },
};
</script>