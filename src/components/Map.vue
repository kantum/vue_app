<template>
  <v-container
    class="ma-0 pa-0"
    >
    <v-flex>
       <iframe width="100%" height="100%" frameborder="0" allowfullscreen src="http://umap.openstreetmap.fr/en/map/untitled-map_405780?scaleControl=false&miniMap=false&scrollWheelZoom=true&zoomControl=true&allowEdit=false&moreControl=false&searchControl=true&tilelayersControl=null&embedControl=null&datalayersControl=true&onLoadPanel=undefined&captionBar=false&datalayers=1124640%2C1124656#4/36.28/8.44"></iframe>
    </v-flex>
  </v-container>
</template>

<script>
export default {
  name: 'Map',

  data () {
    return {
      items: [
        { title: 'Dashboard', icon: 'mdi-view-dashboard' },
        { title: 'Photos', icon: 'mdi-image' },
        { title: 'About', icon: 'mdi-help-box' },
        { title: 'Test', icon: 'mdi-help-box' },
      ],
      right: null,
    }
  },
};
</script>
