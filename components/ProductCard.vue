<template>
  <v-container>
    <v-card variant="elevated" class="mx-auto" :border="false" max-width="400">
      <v-card-item>
        <v-card-title>
          <v-img height="150" :src="product?.image" class="text-white" />
        </v-card-title>
      </v-card-item>
      <v-card-text>
        <p class="truncate font-sans">{{ product?.title }}</p>
      </v-card-text>
      <v-card-actions>
        <v-btn size="small" rounded variant="flat" color="green">
          <NuxtLink :to="`/products/${product?.id}`" class="font-sans truncate">
            SEE MORE DETAILS
          </NuxtLink>
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-container>
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
  .thumb {
    max-height: 120px;
    max-width: 70%;
    margin: 0 auto;
  }
</style>
