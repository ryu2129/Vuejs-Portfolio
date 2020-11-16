<template>
  <v-col cols="12" sm="6" md="4" ls="4">
    <v-card shaped hover class="mx-auto" :ripple="{ center: true}" >
      <v-img
        class="white--text align-end"
        height="200px"
        :src="product.image"
      >
      <v-card-title class="custom-color" >{{ product.name }}</v-card-title>
      </v-img>

      <v-card-subtitle class="pb-0" >{{ product.year }}</v-card-subtitle>

      <v-card-text class="text--promary">
        <div>{{ product.category }}</div>
        <div>{{ product.use }}</div>
        <div>{{ product.info }}</div>
      </v-card-text>

      <v-card-actions class="pb-10">
        <v-btn absolute bottom left color="light-blue darken-2" target="_blank" text :href="product.link">LINK</v-btn>
        <v-btn absolute bottom right color="light-blue darken-2" target="_blank" text :href="product.github">GITHUB</v-btn>
      </v-card-actions>
    </v-card>
  </v-col>
</template>

<script>
export default {
  name: "Product",
  props: ["product"],
};
</script>

<style>
.custom-color {
  color: black;
  background-color: steelblue;
  opacity: 0.6;
}
</style>