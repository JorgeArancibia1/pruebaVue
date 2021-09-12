<template>
	<div class="products">
		<div v-for="(product, index) in products" :key="index">
			<b-card
				title="product.name"
				img-src="product.photo"
				img-alt="product.name"
				img-top
				tag="product"
				style="max-width: 20rem;"
				class="mb-2"
			>
				<b-card-text>
					Precio: ${{product.price}}
				</b-card-text>

				<b-button href="#" variant="primary">Go somewhere</b-button>
			</b-card>
		</div>
	</div>
</template>

<script>
export default {
	name: 'Products',
	components: {},
	data() {
		return {
			products: [],
		};
	},
	methods: {
		async getProducts() {
			const data = await fetch('http://sva.talana.com:8000/api/product/');
			const array = await data.json();
			this.products = array;
			console.log(this.products);
		},
	},
	created() {
		this.getProducts();
	},
};
</script>
