<template>
  <v-app
    id="inspire"
    :style="{ background: $vuetify.theme.themes.dark.background }"
  >
    <SideBar />
    <v-container fluid> </v-container>
  </v-app>
</template>

<script>
import SideBar from "@/components/SideBar.vue";
export default {
  name: "HomePage",

  components: {
    SideBar,
  },
};
</script>
