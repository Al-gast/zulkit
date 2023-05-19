<script setup>
  import { ref } from 'vue';
  import CategoryCard from './CategoryCard.vue';

  const categories = ref([
    {
      id: 1,
      title: "Mobile UI Kit",
      image: 'https://zullkit-backend.demo.belajarkoding.com//storage/gallery/rapHrCh8vTZIs2JQO4v2gmTqPXOo98i5wTOi5IWE.jpg',
      count: 731
    },
    {
      id: 2,
      title: "Fonts",
      image: 'https://zullkit-backend.demo.belajarkoding.com//storage/gallery/x1EiX771YvtUhSH3ajKk58C2iurDHmDKSnZc1wHc.jpg',
      count: 657
    },
    {
      id: 3,
      title: "Icon Set",
      image: 'https://zullkit-backend.demo.belajarkoding.com//storage/gallery/KB0uCZ6iQinGXzYjqBflUFQf7Egbw9xgnS5pilIp.jpg',
      count: 83559
    },
    {
      id: 4,
      title: "Website UI Kit",
      image: 'https://zullkit-backend.demo.belajarkoding.com//storage/gallery/ET8qD9CNo9xNMvdiBTebA4A6SQ9JWrwpO9SK3t5a.jpg',
      count: 4500
    },
  ])
</script>

<template>
  <div class="container px-4 mx-auto my-16 md:px-12">
      <h2 class="mb-4 text-xl font-medium md:mb-0 md:text-lg">Top Categories</h2>
      <div class="flex flex-wrap -mx-1 lg:-mx-4">
      <CategoryCard
          v-for="category in categories"
          :key="category.id"
          :id="category.id"
          :title="category.title"
          :image="category.image"
          :count="category.count"
      />
      </div>
    </div>
</template>

<style lang="scss" scoped>

</style>