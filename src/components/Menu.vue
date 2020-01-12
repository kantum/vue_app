<template>
    <v-list
      class="ma-0 pa-0"
      nav
      >
      <v-list-item
        v-for="item in items"
        :key="item.title"
        @click="item.title"
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>
        </v-list-item>
      </v-list>
</template>

<script>
export default {
  name: 'Menu',

  data () {
    return {
      items: [
        { title: 'J0', icon: 'mdi-view-dashboard' },
        { title: 'J1', icon: 'J1' },
        { title: 'J2', icon: 'J2' },
        { title: 'J3', icon: 'J3' },
        { title: 'J4', icon: 'J4' },
        { title: 'J5', icon: 'J5' },
        { title: 'J6', icon: 'J6' },
        { title: 'J7', icon: 'J7' },
        { title: 'J8', icon: 'J8' },
        { title: 'J9', icon: 'J9' },
        { title: 'JE', icon: 'JE' },
      ],
      right: null,
    }
  },
};
</script>
