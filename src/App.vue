<template>
  <div id="app" class="container mt-5">
    <h1>IDShop</h1>
    <product-list :products="products" :maximum="maximum"></product-list>
    <!-- <p class="animate__animated animate__fadeInRight">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Porro dolor
      voluptas recusandae, possimus nam quam magnam atque distinctio nisi libero
      aspernatur mollitia aliquam, vel sapiente nemo reiciendis aliquid
      dignissimos illo.
    </p>
    <fontAwesomeIcon icon="shopping-cart"></fontAwesomeIcon>
    <ProductPrice :value="4.23"></ProductPrice> -->
  </div>
</template>

<script>
import ProductList from "./components/ProductList.vue";
// import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
// import ProductPrice from "./components/ProductPrice.vue";

export default {
  name: "App",
  data: function () {
    return {
      maximum: 50,
      products: [],
    };
  },
  components: {
    ProductList,
    // FontAwesomeIcon,
    // ProductPrice,
  },
  mounted: function () {
    fetch("https://hplussport.com/api/products/order/price")
      .then((response) => response.json())
      .then((data) => {
        this.products = data;
      });
  },
};
</script>
