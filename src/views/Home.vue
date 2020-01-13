<template >
  <v-container fluid class="ma-0 pa-0 fill-height">
    <v-row class="fill-height" no-gutters style="flex-wrap: nowrap;">
      <Menu v-on:item-selected="menuItemSelected"></Menu>
      <v-flex v-if="selectedMenuItem" class="flex-grow-0 flex-shrink-1">
        <SousMenu1 v-on:item-selected-sub="menuItemSelectedSub" :item="selectedMenuItem"></SousMenu1>
      </v-flex>
      <v-flex v-if="selectedMenuItemSub" class="flex-grow-0 flex-shrink-1">
        <SousMenu2 :item="selectedMenuItemSub"></SousMenu2>
      </v-flex>
      <v-flex class="flex-grow-1 flex-shrink-0">
        <Map></Map>
      </v-flex>
    </v-row>
  </v-container>
</template>

<script>
// @ is an alias to /src
import Menu from "@/components/Menu.vue";
import SousMenu1 from "@/components/SousMenu1.vue";
import SousMenu2 from "@/components/SousMenu2.vue";
import Map from "@/components/Map.vue";

export default {
  name: "home",
  components: {
    Menu,
    SousMenu1,
    SousMenu2,
    Map
  },
  data() {
    return {
      selectedMenuItem: null,
      selectedMenuItemSub: null,
      selectedMenuItemSubDetail: null
    };
  },
  methods: {
    menuItemSelected(item) {
      this.selectedMenuItem = item;
    },
    menuItemSelectedSub(item) {
      this.selectedMenuItemSub = item;
    }
  }
};
</script>