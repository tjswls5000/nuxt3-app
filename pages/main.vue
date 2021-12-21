<template>
  <div>
    <p>main page</p>
    <ol>
      <li v-for="(product, index) in products">
        {{ product.name }}: {{ product.price }}$
      </li>
    </ol>
  </div>
</template>

<script setup lang="ts">
interface Product {
  id: number
  name: string
  price: string
  imageUrl: string
}
const { data } = await useFetch<string,Array<Product>>('http://localhost:3000/products')//,{pick: ['name', 'price']}
const products: Array<Product> = data.value;
</script>


<style scoped>
</style>