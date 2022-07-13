<template>
  <div>
    <header>
      <button v-on:click="navigateTo('products')">View Products</button>
      {{ cart.length }} in cart
      <button v-on:click="navigateTo('cart')">View Cart</button>
    </header>

    <div v-if="page === 'cart'">
      <h1>Your Cart</h1>
      <div class="products">
        <div v-for="product in cart" :key="product.name">
          {{ product.name }}
          <img :src="product.image" />
          <div>{{ product.cost }}</div>
          <button v-on:click="removeItemFromCart(product)">
            Remove from cart
          </button>
        </div>
      </div>
    </div>

    <div v-if="page === 'products'">
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
  </div>
</template>

<script>
export default {
  name: 'App',
  data: () => {
    return {
      page: 'products',
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
            'https://www.recipetineats.com/wp-content/uploads/2017/06/Soft-Chocolate-Chip-Cookies-3.jpg?w=500&h=500&crop=1',
        },
      ],
    };
  },
  methods: {
    addItemToCart(product) {
      this.cart.push(product);
      console.log(this.cart);
    },
    removeItemFromCart(product) {
      this.cart.splice(this.cart.indexOf(product));
    },
    navigateTo(page) {
      this.page = page;
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
  height: 60px;
  background-color: #eee;
  box-shadow: 2px 2px 5px #999;
  text-align: right;
  font-size: 30px;
  padding-top: 20px;
}
</style>
