<template>
  <v-container>
    <div class="text-right">
      <v-bottom-sheet top >
        <template v-slot:activator="{ on }">
          <v-btn color="primary" dark v-on="on">Timeline</v-btn>
        </template>
<iframe src='https://cdn.knightlab.com/libs/timeline3/latest/embed/index.html?source=1_a7AZhNoGYk0Eks4pO8gaFntWGEO-4FMMkJQ_5CNSws&font=Default&lang=en&initial_zoom=2&height=400' width='100%' height='400' webkitallowfullscreen mozallowfullscreen allowfullscreen frameborder='0'></iframe>
      </v-bottom-sheet>
    </div>
  </v-container>
</template>

<script>
export default {
  name: "TimeLine",

};
</script>