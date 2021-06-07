<template>
  <div class="grid-wrap">
    <ProductsGridItem
      v-for="product in products"
      :key="product.id"
      :product="product"
    />
  </div>
</template>

<script>
import ProductsGridItem from './ProductsGridItem';

export default {
	name:"ProductsGrid",
	props:['products'],
	components: {
		ProductsGridItem
	}
}
</script>
