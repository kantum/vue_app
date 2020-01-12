<template>
  <v-container class="ma-0 pa-0">
    <v-list>
      <v-list-item>{{ this.$options.name }}</v-list-item>
    </v-list>
    <v-list nav>
      <v-list-item>
        <span>current menu: {{ item.menu}}</span>
      </v-list-item>
      <v-list-item v-for="item in items" :key="item.title" @click="selectItemSub(item)">
        <v-list-item-icon>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-item-icon>
        <v-list-item-content>
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-container>
</template>

<script>
export default {
  name: "SousMenu1",

  data() {
    return {
      items: [
        { title: "Dashboard", icon: "mdi-view-dashboard" },
        { title: "Photos", icon: "mdi-image" },
        { title: "About", icon: "mdi-help-box" },
        { title: "Test", icon: "mdi-help-box" }
      ],
      right: null
    };
  },
  props: {
    item: Object
  },
  methods: {
    selectItemSub(item) {
      this.$emit("item-selected-sub", item);
    }
  }
};
</script>
