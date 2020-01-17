<template >
  <v-container fluid class="ma-0 pa-0">
    <v-app-bar-nav app>
      <v-row justify="end" style=" height: 74px; flex-wrap: nowrap;">
        <v-col>
          <div style="margin-left: 20px">
            <v-img width="50px" aspect-ratio="1" :src="require('../assets/logo.svg')" />
          </div>
        </v-col>
        <v-col></v-col>
        <v-col></v-col>
        <v-col class="ma-0 pa-0">
          <Date></Date>
        </v-col>
      </v-row>
    </v-app-bar-nav>
    <v-row style="flex-wrap: nowrap; height: calc( 100vh - 74px - 74px) " no-gutters>
      <Menu v-on:item-selected="menuItemSelected"></Menu>
      <v-col v-if="selectedMenuItem" class="flex-grow-0 flex-shrink-1">
        <SousMenu1 v-on:item-selected-sub="menuItemSelectedSub" :item="selectedMenuItem"></SousMenu1>
      </v-col>
      <v-col v-if="selectedMenuItemSub" class="flex-grow-0 flex-shrink-1">
        <SousMenu2 :item="selectedMenuItemSub"></SousMenu2>
      </v-col>
      <v-col class="flex-grow-1 flex-shrink-0" no-gutters>
        <Map></Map>
      </v-col>
    </v-row>
    <v-footer style="height: 74px" absolute>
      <v-row style="flex-wrap: nowrap;" class="ma-0 pa-0">
        <v-switch color="primary" v-model="switch3"></v-switch>
      </v-row>
      <v-row class="ma-0 pa-0">
        <TimeLine></TimeLine>
      </v-row>
      <v-row class="ma-0 pa-0">
        <Message></Message>
      </v-row>
      <Form></Form>
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
import TimeLine from "@/components/TimeLine.vue";
import Form from "@/components/Form.vue";

export default {
  name: "home",
  components: {
    Menu,
    SousMenu1,
    SousMenu2,
    Map,
    Message,
    Date,
    TimeLine,
    Form
  },
  data() {
    return {
      selectedMenuItem: null,
      selectedMenuItemSub: null,
      selectedMenuItemSubDetail: null,
      switch: false
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