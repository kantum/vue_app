<template>
  <v-menu top :offset-y="offset">
    <template v-slot:activator="{ on }">
      <v-btn color="primary" dark v-on="on">J-chat</v-btn>
    </template>
    <v-list>
      <v-card>
        <v-list-item v-for="(item, index) in messages" :key="index">
          <v-list-item-title>{{ item.user }}</v-list-item-title>
          <v-list-item-title>{{ item.text }}</v-list-item-title>
        </v-list-item>
      </v-card>
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
      items: [{ title: "Message 1" }],
      offset: true,
      sheet: false
    };
  },
  methods: {
    sendMessage(message) {
      this.$emit("message", message);
    }
  }
};
</script>