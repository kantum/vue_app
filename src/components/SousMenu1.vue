<template>
  <v-container class="ma-0 pa-0">
    <v-list-item>
      <span>{{ item.title }}</span>
    </v-list-item>
    <v-list nav>
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
        { title: "Existants", icon: "mdi-docker" },
        { title: "Disponibilités", icon: "mdi-help-box" },
        { title: "Infrastructure", icon: "mdi-home-city" },
        { title: "Médical", icon: "mdi-doctor" }
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
