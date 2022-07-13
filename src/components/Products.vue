<template>
  <div>
    <h1>Products</h1>
    <div class="products">
      <div v-for="(product, index) in products" :key="index">
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
  data: () => {
    return {
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
      this.$emit('addItemToCart', product);
    },
  },
};
</script>

<style></style>
