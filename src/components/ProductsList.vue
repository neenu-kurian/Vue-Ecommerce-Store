<template>
  <div class="grid-wrap">
    <ProductsListItem
      v-for="product in products"
      :key="product.id"
      :product="product"
    />
  </div>
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