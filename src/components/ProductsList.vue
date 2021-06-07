<template>
  <div v-if="products.length>0" class="grid-wrap">
    <ProductsListItem
      v-for="product in products"
      :key="product.id"
      :product="product"
    />
  </div>
  <p v-else>You havent added any product to your cart</p>
</template>

<script>
import ProductsListItem from './ProductsListItem.vue';

export default {
  name: 'ProductsList',
  props: ['products'],
  components: {
    ProductsListItem,
  },
};
</script>

<style scoped>
.grid-wrap {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  margin-top: 16px;
}
</style>