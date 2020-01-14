<template>
<v-container>
<div class="text-right">
  <v-bottom-sheet scrollable max-width="100px" no-click-animation hide-overlay="1" persistent>
    <template v-slot:activator="{ on }">
      <v-btn
        color="green"
        dark
        v-on="on"
      >
messages
      </v-btn>
    </template>
      <v-list>
        <v-list-item v-for="message in messages" :key="message" link>
          <v-list-item-title v-text=" message.text"></v-list-item-title>
        </v-list-item>
      </v-list>
  </v-bottom-sheet>
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
      items: [
       { title: "Message 1" },
      ],
      offset: true,
      sheet: false,
    };
  },
  methods: {
    sendMessage(message) {
      this.$emit("message", message);
    }
  }
};
</script>