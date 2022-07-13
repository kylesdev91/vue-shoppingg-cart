<template>
  <div>
    <h1>Your Cart</h1>
    <div class="products">
      <div v-for="(product, index) in cart" :key="index">
        {{ product.name }}
        <img :src="product.image" />
        <div>{{ product.cost }}</div>
        <button v-on:click="removeItemFromCart(product)">
          Remove from cart
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['cart'],
  methods: {
    removeItemFromCart(product) {
      this.$emit('removeItemFromCart', product);
    },
  },
};
</script>

<style></style>
