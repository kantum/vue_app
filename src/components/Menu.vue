<template>
  <v-navigation-drawer
    class="ma-0 pa-0"
    mini-variant
    >
  <v-list
    class="ma-0 pa-0"
    nav
    >
    <v-list-item
      v-for="item in items"
      :key="item.title"
      @click="item.menu = !item.menu"
      >
      <v-list-item-icon>
        <v-icon>{{ item.icon }}</v-icon>
      </v-list-item-icon>
    <v-list-item-content>
      <v-list-item-title>{{ item.title }}</v-list-item-title>
    </v-list-item-content>
    </v-list-item>
  </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
  name: 'Menu',

  data () {
    return {
      items: [
        { title: '', icon: 'mdi-view-dashboard', menu: 'j0'},
        { title: '', icon: 'J1', menu: 'j1' },
        { title: '', icon: 'J2', menu: 'j2' },
        { title: '', icon: 'J3', menu: 'j3' },
        { title: '', icon: 'J4', menu: 'j4' },
        { title: '', icon: 'J5', menu: 'j5' },
        { title: '', icon: 'J6', menu: 'j6' },
        { title: '', icon: 'J7', menu: 'j7' },
        { title: '', icon: 'J8', menu: 'j8' },
        { title: '', icon: 'J9', menu: 'j9' },
        { title: '', icon: 'JE', menu: 'jE' },
      ],
      j0: null,
      j1: null,
      j2: null,
      j3: null,
      j4: null,
      j5: null,
      j6: null,
      j7: null,
      j8: null,
      j9: null,
      jE: null,
    }
  },
};
</script>
