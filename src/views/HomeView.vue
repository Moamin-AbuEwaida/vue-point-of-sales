<template>
  <v-app
    id="inspire"
    :style="{ background: $vuetify.theme.themes.dark.background }"
  >
    <SideBar />
    <NavBar />
    <v-container fluid> </v-container>
  </v-app>
</template>

<script>
import SideBar from "@/components/SideBar.vue";
import NavBar from "@/components/NavBar.vue";
export default {
  name: "HomePage",

  components: {
    SideBar,
    NavBar,
  },
};
</script>
