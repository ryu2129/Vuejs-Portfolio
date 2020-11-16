<template>
  <div>
    <ProductHeader @sortCategoryChange="sortCategoryChanged($event)"></ProductHeader>
    <v-row>
      <product
        v-for="(product, key) in filterdList"
        :key="key"
        :product="product"
      ></product>
    </v-row>
  </div>
</template>

<script>
import ProductHeader from "./ProductHeader.vue";
import Product from "./Product.vue";

export default {
  name: "ProductList",
  components: { ProductHeader, Product },
  data: () => ({
    sortCategory: "ALL",
    products: [
      {
        id: 1,
        name: "パーソナルトレーニング予約サイト",
        image: require("../assets/works/personal.png"),
        year: "2020",
        category: "LP",
        use: "html css JS PHP",
        link: "https://www.hocchi-tetsuya.com/",
        info: "",
      },
      {
        id: 2,
        name: "Parrot",
        image: require("../assets/works/parrot.png"),
        year: "2020",
        category: "APP",
        use: "html css JS Ruby on Rails",
        link: "https://parrot-live.work/",
        github: "https://github.com/ryu2129/Parrot",
        info: "",
      },
      {
        id: 3,
        name: "Chatbot",
        image: require("../assets/works/chatobot.png"),
        year: "2020",
        category: "APP",
        use: "html css React",
        info: "",
      },
      {
        id: 4,
        name: "Portfolio",
        image: require("../assets/works/vue-porfolio.png"),
        year: "2020",
        category: "SPA",
        use: "Vue.js",
        info: "",
      },
    ],
  }),
  computed: {
    filterdList: function() {
      const newList = [];
      for (let i = 0; i < this.products.length; i++) {
        if(
          this.sortCategory === "LP" &&
          this.products[i].category === "LP"
          ) {
          newList.push(this.products[i]);
        } else if (
          this.sortCategory === "APP" &&
          this.products[i].category === "APP"
        ) {
          newList.push(this.products[i]);
        } else if (
          this.sortCategory === "SPA" &&
          this.products[i].category === "SPA"
        ) {
          newList.push(this.products[i]);
        } else if (this.sortCategory === "ALL") {
          newList.push(this.products[i]);
        }
      }
      return newList;
    },
  },
  methods: {
    sortCategoryChanged: function(category) {
      console.log(category);
      this.sortCategory = category;
    },
  },
};
</script>