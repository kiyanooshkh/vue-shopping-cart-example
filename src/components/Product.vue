<template>
  <div class="product">
    <div class="product-image">
      <img src="../assets/logo.png">
    </div>
    <div class="product-info">
      <h1>{{product}}</h1>
      <p v-if="inventory > 10">In stock</p>
      <p v-else-if="inventory <= 1 && inventory > 0">Almost sold out</p>
      <p v-else>Out of stock</p>
      <ul>
        <li v-for="detail in details" :key="detail">{{detail}}</li>
      </ul>
      <ul>
        <li v-for="variant in variants" :key="variant.variantId">{{variant.variantColor}}</li>
      </ul>
      <div>
        <p id="cart">Cart ({{cart}})</p>
      </div>
      <button v-on:click="addtoCart">Add to cart</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Product",
  props: {
    product: String,
    image: String,
    inventory: Number,
    details: Array,
    variants: Object,
    cart: Number,
    addtoCart: Function
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.product-image img {
  margin: 25px;
  float: left;
  width: 200px;
  height: 200px;
}
</style>