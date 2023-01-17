<template>
  <v-navigation-drawer
    v-model="drawer"
    app
    dark
    color="#323b50"
    mini-variant
    mini-variant-width="90"
  >
    <v-avatar class="d-block text-center mx-auto mt-4 border_img" size="40">
      <v-img src="https://cdn.vuetifyjs.com/images/lists/1.jpg"></v-img>
    </v-avatar>
    <v-list flat class="mt-5">
      <v-list-item-group v-model="selectedItem">
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          active-class="border"
          v-slot="{ active }"
          :ripple="false"
        >
          <v-list-item-icon>
            <div :class="active ? 'a' : ''"></div>
            <v-icon
              v-text="item.icon"
              :color="active ? '#f34f64' : '#778290'"
            ></v-icon>
          </v-list-item-icon>
        </v-list-item>
      </v-list-item-group>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
  data: () => ({
    selectedItem: 0,
    drawer: null,
    items: [
      { icon: "mdi-laptop" },
      { icon: "mdi-tag-outline" },
      { icon: "mdi-shopping-outline" },
      { icon: "mdi-wallet-travel" },
      { icon: "mdi-apps" },
      { icon: "mdi-text-box-multiple-outline" },
    ],
  }),
};
</script>

<style>
.a {
  position: absolute;
  top: 50%;
  left: 2%;
  transform: translate(-50%, -50%);
  height: 18px;
  width: 12px;
  border-radius: 0px 150px 150px 0px;
  background-color: #f34f64;
}
.border_img {
  border: 1px solid #728290;
}
.border {
  text-decoration: none;
}
.v-list-item-group .v-list-item--active {
  color: white !important;
}
.theme--light.v-list-item--active .v-list-item__subtitle,
.theme--light.v-list-item.v-list-item__action-text {
  color: white !important;
}
</style>
