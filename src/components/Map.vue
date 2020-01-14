<template>
  <iframe
    width="100%"
    height="100%"
    frameborder="0"
    allowfullscreen
    src="https://umap.openstreetmap.fr/en/map/untitled-map_406649?scaleControl=true&miniMap=false&scrollWheelZoom=false&zoomControl=true&allowEdit=false&moreControl=false&searchControl=null&tilelayersControl=null&embedControl=null&datalayersControl=true&onLoadPanel=undefined&captionBar=false"
  ></iframe>
</template>

<script>
export default {
  name: "Map",

  data() {
    return {
      right: null
    };
  }
};
</script>
