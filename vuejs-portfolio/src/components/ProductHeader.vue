<template>
  <v-flex align-end>
    <v-col class="px-0" cols="12" sm="6">
      <v-select
        :items="items"
        label="sort"
        outlined
        @change="sort"
        v-model="category"
      ></v-select>
    </v-col>
  </v-flex>
</template>

<script>
export default {
  name: "ProductHeader",
  props: ["sortCategory"],
  data: () => ({
    items: ["ALL", "LP", "APP", "SPA"],
    category: "ALL",
  }),
  methods: {
    sort: function() {
      this.$emit("sortCategoryChange", this.category);
    },
  },
};
</script>