<template>
  <div class="card">
    <main class="grid grid-cols-2 gap-10">
      <article class="p-7">
        <img :src="product.image" alt="product image" class="mx-auto my-7" />
      </article>
      <article class="p-7">
        <h2 class="text-4xl my-7">
          {{ product.title }}
        </h2>
        <p class="text-xl my-7">Price - ${{ product.price }}</p>
        <h3 class="font-bold border-b-2 mb-4 pb-2">Product description:</h3>
        <p class="mb-7">{{ product.description }}</p>
        <button class="btn flex">
          <i class="material-icons mr-2">add_shopping_cart</i>
          <span>Add to cart</span>
        </button>
      </article>
    </main>
  </div>
</template>

<script setup lang="ts">
  import { PropType } from 'vue'
  import { Products } from '~~/types/Products/products'

  defineProps({
    product: {
      type: Object as PropType<Products>,
    },
  })
</script>

<style scoped>
  img {
    max-width: 400px;
  }
</style>
