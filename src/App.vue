<template>
  <div>
    <h1>Products</h1>
    <div v-for="product in products" :key="product.name">
      {{ product.name }}
      <img :src="product.image" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data: () => {
    return {
      products: [
        {
          name: 'Hair Brush',
          cost: '0.99',
          image:
            'https://m.aveda.com/media/images/products/355x600/av_sku_ATL301_104746_355x600_0.jpg',
        },
      ],
    };
  },
  components: {},
};
</script>

<style></style>
