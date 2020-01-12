<template >
    <v-row
      class="ma-0 pa-0 fill-height"
      >
      <v-flex
      class="ma-0 pa-0 fill-height blue"
      >
        <Menu msg="Welcome to Your Vue.js App"/>
      </v-flex>
      <v-flex class="red">
        <SousMenu1 msg="hello"/>
      </v-flex>
    <v-flex class="purple">
      <SousMenu2 msg="hello"/>
    </v-flex>
  <v-flex class="green">
    <Map/>
  </v-flex>
    </v-row>
</template>

<script>
// @ is an alias to /src
  import Menu from '@/components/Menu.vue'
import SousMenu1 from '@/components/SousMenu1.vue'
import SousMenu2 from '@/components/SousMenu2.vue'
import Map from '@/components/Map.vue'

export default {
  name: 'home',
  components: {
    Menu,
    SousMenu1,
    SousMenu2,
    Map
  }
}
</script>
