<template>
	<div id="page-wrap" v-if="product">
		<div id="img-wrap">
			<img v-bind:src="product.imageUrl" />
		</div>
		<div id="product-details">
			<h1>{{ product.name }}</h1>
			<h3 id="price">${{ product.price }}</h3>
			<p>Average Rating: {{ product.averageRating }}</p>
			<button id="add-to-cart" v-if="!showSuccessMessage" v-on:click="addToCart">Add to Cart</button>
			<button id="add-to-cart" v-if="showSuccessMessage" class="green-button">Successfully added item in cart</button>
			<h4>Description</h4>
			<p>{{ product.description }}</p>
		</div>
	</div>
	<NotFoundPage v-else />
</template>

<script>
import axios from 'axios';
import NotFoundPage from './NotFoundPage';

export default {
	name: 'ProductDetailPage',
	components: {
		NotFoundPage,
	},
	data() {
		return {
			product:{},
			showSuccessMessage: false,
		};	
	},
	methods: {
		async addToCart(){
			await axios.post('/api/users/12345/cart',{
				productId: this.$route.params.id
			});

			this.showSuccessMessage=true;

			setTimeout(()=>{
				this.$router.push('/products')
			},1500);

		}
	},
	async created(){
		const result = await axios.get(`/api/products/${this.$route.params.id}`);
		const product = result.data;
		this.product = product;
	}
};
</script>

<style scoped>
#page-wrap {
	margin-top: 16px;
	padding: 16px;
	max-width: 600px;
}

#img-wrap {
	text-align: center;
}

img {
	width: 400px;
}

#product-details {
	padding: 16px;
	position: relative;
}

#add-to-cart {
	width: 100%;
  background: transparent;
  color: #006a89;
  border: 1px solid #006a89;
  border-radius: 0;
}


#add-to-cart:hover {
  background: #006a89;
  color: white;
  border: 1px solid #006a89;
}


#price {
	position: absolute;
	top: 24px;
	right: 16px;
}

.green-button {
	background-color: green;
}
</style>
