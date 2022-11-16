<template>
  <div>
    <Head>
      <Title>Nuxt Dojo | {{ product.title }}</Title>
      <Meta name="description" :content="product.description" />
    </Head>
    <ProductDetail :product="product" />
  </div>
</template>

<script setup lang="ts">
  import { Products } from '~~/types/Products/products'

  const { id } = useRoute().params
  const uri = `https://fakestoreapi.com/products/${id}`

  // fetch the product
  const { data: product } = await useFetch<Products>(uri, { key: id as string })

  if (!product.value) {
    throw createError({
      statusCode: 404,
      statusMessage: 'Product not found',
      fatal: true,
    })
  }

  definePageMeta({
    layout: 'products',
  })
</script>
