<template>
  <v-menu fixed bottom close-on-content-click="false" close-on-click="false" top :offset-y="offset">
    <template v-slot:activator="{ on }">
      <v-btn color="primary" dark v-on="on">J-chat</v-btn>
    </template>
    <v-card height="500px" class="mx-auto">
      <v-list>
        <v-list-item-group color="primary">
          <v-list-item
            v-for="(item, i) in messages"
            :key="i"
            :class="(item.sent ? 'text-right' : '')"
          >
            <v-chip pill v-if="item.sent">
              {{ item.msg }}
              <v-avatar right>
                <v-img src="https://cdn.vuetifyjs.com/images/john.png"></v-img>
              </v-avatar>
            </v-chip>
            <v-chip pill v-else>
              <v-avatar left>
                <v-img src="https://cdn.vuetifyjs.com/images/john.png"></v-img>
              </v-avatar>
              {{ item.msg }}
            </v-chip>
          </v-list-item>
          <v-list-item>
            <v-textarea
              append-outer-icon="send"
              @click:append-outer="sendMessage"
              v-model="messageNew.text"
              class="mx-1"
              label="Message to send"
              rows="2"
            ></v-textarea>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-card>
  </v-menu>
</template>

<script>
export default {
  name: "Message",

  data() {
    return {
      items: [
        {
          active: true,
          title: "Jason Oner",
          avatar: "https://cdn.vuetifyjs.com/images/lists/1.jpg"
        },
        {
          active: true,
          title: "Ranee Carlson",
          avatar: "https://cdn.vuetifyjs.com/images/lists/2.jpg"
        },
        {
          title: "Cindy Baker",
          avatar: "https://cdn.vuetifyjs.com/images/lists/3.jpg"
        },
        {
          title: "Ali Connors",
          avatar: "https://cdn.vuetifyjs.com/images/lists/4.jpg"
        }
      ],
      messageNew: {
        text: null
      },
      messages: [
        {
          msg: "Real-Time",
          avatar:
            "https://s1.lemde.fr/media/img/personalities/228cfe4_8695-jc8mfh.t0a8257b9.jpg",
          sent: false
        },
        {
          msg: "Audience",
          avatar:
            "https://s1.lemde.fr/media/img/personalities/228cfe4_8695-jc8mfh.t0a8257b9.jpg",
          sent: true
        },
        {
          msg: "Conversions",
          avatar: "https://cdn.vuetifyjs.com/images/john.png",
          sent: false
        },
        {
          msg: "reaas",
          avatar: "https://cdn.vuetifyjs.com/images/john.png",
          sent: false
        }
      ],
      offset: true,
      sheet: false
    };
  },
  methods: {
    sendMessage() {
      this.messages.push({
        msg: this.messageNew.text,
        avatar:
          "https://s1.lemde.fr/media/img/personalities/228cfe4_8695-jc8mfh.t0a8257b9.jpg",
        sent: true
      });
      this.messageNew.text = null;
    }
  }
};
</script>