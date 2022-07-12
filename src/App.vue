<template>
  <div>
    <header>{{ cart.length }} in cart</header>
    <h1>Products</h1>
    <div class="products">
      <div v-for="product in products" :key="product.name">
        {{ product.name }}
        <img :src="product.image" />
        <div>{{ product.cost }}</div>
        <button v-on:click="addItemToCart(product)">Add to cart</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data: () => {
    return {
      cart: [],
      products: [
        {
          name: 'Hair Brush',
          cost: '$0.99',
          image:
            'https://m.aveda.com/media/images/products/355x600/av_sku_ATL301_104746_355x600_0.jpg',
        },
        {
          name: 'Cookies',
          cost: '$5.99',
          image:
            'https://www.inkatrinaskitchen.com/wp-content/uploads/2012/03/Rainbow-Chocolate-Chip-Cookies-Recipe-In-Katrinas-Kitchen-600.jpg',
        },
      ],
    };
  },
  methods: {
    addItemToCart(product) {
      this.cart.push(product);
      console.log(this.cart);
    },
  },
  components: {},
};
</script>

<style>
body {
  margin: 0;
}
</style>
<style scoped>
.products {
  display: grid;
  grid-template-columns: 1fr 1fr;
}

header {
  height: 100px;
  background-color: #ddd;
}
</style>
