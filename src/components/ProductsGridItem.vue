<template>
  <div class="product-item">
    <img v-bind:src="product.imageUrl" />
    <h3 class="product-name">{{ product.name }}</h3>
    <p class="product-price">${{ product.price }}</p>
    <router-link v-bind:to="'/products/' + product.id">
      <button>View Details</button>
    </router-link>
  </div>
</template>

<script>
export default {
	name:'ProductsGridItem',
	props:['product'],
}
</script>

<style scoped>
.product-item {
  align-items: center;
  box-shadow: 0px 2px 5px #888;
  display: flex;
  flex-direction: column;
  margin-bottom: 2%;
  padding: 20px;
  position: relative;
  width: 23%;
}

.product-name {
  margin-bottom: 0;
}

img {
  height: 200px;
  width: 100%;
}

a {
  width: 100%;
}

button {
  width: 100%;
  background: transparent;
  color: #006a89;
  border: 1px solid #006a89;
  border-radius: 0;
}

button:hover {
  background: #006a89;
  color: white;
  border: 1px solid #006a89;
}

</style>