<template>
<v-container>
    <v-menu
      ref="menu"
      v-model="menu"
      :close-on-content-click="false"
      :return-value.sync="date"
      transition="scale-transition"
      offset-y
      min-width="290px"
    >
      <template v-slot:activator="{ on }">
        <v-text-field
          v-model="date"
          label="Date"
          v-on="on"
        ></v-text-field>
      </template>
      <v-date-picker
      v-model="date" no-title scrollable>
        <v-btn text color="primary" @click="menu = false">Cancel</v-btn>
        <v-btn text color="primary" @click="$refs.menu.save(date)">OK</v-btn>
      </v-date-picker>
    </v-menu>
</v-container>
</template>

<script>
export default {

  name: 'Date',
  data() {
    return {
        menu: false,
        date: new Date().toISOString().substr(0, 10),
  }
  }
};
</script>