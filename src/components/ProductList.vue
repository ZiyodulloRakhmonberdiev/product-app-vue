<template>
  <div class="product__list" v-if="products.length > 0">
    <Product
      v-for="product in products"
      :product="product"
      :key="product.id"
      @remove="$emit('remove', product)"
    />
  </div>
  <div v-else class="not__found">
    <p class="not__found-text">
      There is no product. Because you turned them off. <br />
      You can add them via the form. It is on the left side of the screen.
    </p>
  </div>
</template>
<script>
import Product from "./Product";
export default {
  props: {
    products: {
      type: Array,
      required: true,
    },
  },
  components: {
    Product,
  },
};
</script>
<style scoped>
.product__list {
  display: flex;
  justify-content: start;
  flex-wrap: wrap;
}
.not__found {
  width: 60%;
  display: flex;
  /* align-items: center; */
  justify-content: center;
}
.not__found-text {
  font-size: 24px;
  color: #3f3f3f;
  text-align: center;
}
</style>
