<template >
  <v-container fluid class="ma-0 pa-0">
    <v-row app style="flex-wrap: nowrap;" no-gutters>
      <h1>hello</h1>
    </v-row>
    <v-row app style="flex-wrap: nowrap;" class="fill-height" no-gutters>
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
    <div class="float-right">
      <v-flex class="flex-grow-1 flex-shrink-0" no-gutters>
      <Message ></Message>
    </v-flex>
    </div>
  </v-container>
</template>

<script>
// @ is an alias to /src
import Menu from "@/components/Menu.vue";
import SousMenu1 from "@/components/SousMenu1.vue";
import SousMenu2 from "@/components/SousMenu2.vue";
import Map from "@/components/Map.vue";
import Message from "@/components/Message.vue";

export default {
  name: "home",
  components: {
    Menu,
    SousMenu1,
    SousMenu2,
    Map,
    Message
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