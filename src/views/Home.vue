<template>
  <v-container fluid>
    <v-row class="fill-height">
      <v-col class="blue">
        <Menu msg="Welcome to Your Vue.js App"/>
      </v-col>
      <v-col class="red">
        <SousMenu1 msg="hello"/>
      </v-col>
      <v-col class="green">
        <Map/>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
// @ is an alias to /src
import Menu from '@/components/Menu.vue'
import SousMenu1 from '@/components/SousMenu1.vue'
import Map from '@/components/Map.vue'

export default {
  name: 'home',
  components: {
    Menu,
    SousMenu1,
    Map
  }
}
</script>
