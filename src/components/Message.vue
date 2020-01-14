<template>
  <v-menu top :offset-y="offset">
    <template v-slot:activator="{ on }">
      <v-btn color="primary" dark v-on="on">Dropdown</v-btn>
    </template>

    <v-list>
      <v-list-item v-for="(item, index) in items" :key="index" @click="on">
        <v-list-item-title>{{ item.title }}</v-list-item-title>
      </v-list-item>
    </v-list>
  </v-menu>
</template>

<script>
export default {
  name: "Message",

  data() {
    return {
      messages: [
        { user: "bob", text: "Salut Bob" },
        { user: "John", text: "Salut John" }
      ],
      items: [
        { title: "Message 1" },
        { title: "Message 2" },
        { title: "Message 3" },
        { title: "Message 4" },
        { title: "Message 5" },
        { title: "Message 6" }
      ],
      offset: true
    };
  },
  methods: {
    sendMessage(message) {
      this.$emit("message", message);
    }
  }
};
</script>