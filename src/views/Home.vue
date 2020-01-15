<template >
  <v-container fluid fill-height class="ma-0 pa-0">
    <v-row justify="end" style="flex-wrap: nowrap;">
      <v-col></v-col>
      <v-col></v-col>
      <v-col></v-col>
      <v-col class="ma-0 pa-0">
        <Date></Date>
      </v-col>
    </v-row>
    <v-row style="flex-wrap: wrap;" class="fill-height" no-gutters>
      <Menu v-on:item-selected="menuItemSelected"></Menu>
      <v-flex v-if="selectedMenuItem" class="flex-grow-0 flex-shrink-1">
        <SousMenu1 v-on:item-selected-sub="menuItemSelectedSub" :item="selectedMenuItem"></SousMenu1>
      </v-flex>
      <v-flex v-if="selectedMenuItemSub" class="flex-grow-0 flex-shrink-1">
        <SousMenu2 :item="selectedMenuItemSub"></SousMenu2>
      </v-flex>
      <v-flex class="flex-grow-1 flex-shrink-0" no-gutters>
        <Map></Map>
      </v-flex>
    </v-row>
    <v-footer absolute>
      <Message></Message>
    </v-footer>
  </v-container>
</template>

<script>
// @ is an alias to /src
import Menu from "@/components/Menu.vue";
import SousMenu1 from "@/components/SousMenu1.vue";
import SousMenu2 from "@/components/SousMenu2.vue";
import Map from "@/components/Map.vue";
import Message from "@/components/Message.vue";
import Date from "@/components/Date.vue";

export default {
  name: "home",
  components: {
    Menu,
    SousMenu1,
    SousMenu2,
    Map,
    Message,
    Date
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
      if (item === this.selectedMenuItem) {
        this.selectedMenuItem = null;
        this.selectedMenuItemSub = null;
      } else {
        this.selectedMenuItem = item;
      }
    },
    menuItemSelectedSub(item) {
      if (item === this.selectedMenuItemSub) {
        this.selectedMenuItemSub = null;
      } else {
        this.selectedMenuItemSub = item;
      }
    }
  }
};
</script>