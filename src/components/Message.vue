<template>
<v-container>
<div class="text-right">
  <v-bottom-sheet
  inset max-width="420px"
  hide-overlay="1"
  persistent
  >
    <template v-slot:activator="{ on }">
      <v-btn
        color="green"
        v-on="on"
      >
messages
      </v-btn>
    </template>
        <v-sheet class="text-right" height="200px">
      <v-list>
        <v-list-item v-for="message in messages" :key="message" link>
          <v-list-item-title v-text=" message.text"></v-list-item-title>
        </v-list-item>
          <v-text-field
            label="Votre message"
            solo
          ></v-text-field>
        <v-btn>
          Envoyer
        </v-btn>
        </v-list>
        </v-sheet>
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