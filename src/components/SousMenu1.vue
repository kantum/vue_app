<template>
  <v-container class="ma-0 pa-0">
      <v-list-item-group>
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
    <v-alert
      max-width="400px"
      class="ma-1"
      border="left"
      icon="mdi-account"
      tile
      elevation="4"
      v-for="message in messages"
      :key="message.j"
    >
      {{ message.j }}
      <br />
      {{ message.text }}
    </v-alert>
      </v-list-item-group>
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
      messages: [
        { j: "J3", text: "Ça va chier des bulles !" },
        {
          j: "J2",
          text: "Mines antipersonnel décourverte au collège Saint Martin"
        },
        { j: "JE", text: "Au bal ! Au bal masqué ohé ohé !" }
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
