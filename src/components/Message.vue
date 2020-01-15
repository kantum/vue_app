<template>
  <v-container fluid>
    <div class="text-right">
      <v-menu top :offset-y="offset">
        <template v-slot:activator="{ on }">
          <v-btn color="primary" dark v-on="on">Messages</v-btn>
        </template>
        <v-list>
          <v-list-item v-for="(item, index) in items" :key="index">
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </div>
  </v-container>
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