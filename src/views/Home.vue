<template >
  <v-container
    fluid
    class="ma-0 pa-0 fill-height"
    >
    <v-row
      class="fill-height"
      >
      <Menu></Menu>
      <v-flex class="red">
        <SousMenu1></SousMenu1>
      </v-flex>
  <v-flex class="purple" >
    <SousMenu2></SousMenu2>
  </v-flex>
  <v-flex class="green">
    <Map></Map>
  </v-flex>
    </v-row>
  </v-container>
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
