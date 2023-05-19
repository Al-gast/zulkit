<script setup>
  import { ref } from 'vue';
  import ItemCard from './ItemCard.vue';

  const items = ref([
    {
      id: 1,
      title: "RoboCrypto UI Kit",
      image: 'https://zullkit-backend.demo.belajarkoding.com//storage/gallery/8LHRvjUTIYvzmGM5JNm3Z1L3VfWd6JffMIkR00rf.png',
      description: "Build your next coin startup"
    },
    {
      id: 2,
      title: "Online Doctor Consultation",
      image: "https://zullkit-backend.demo.belajarkoding.com//storage/gallery/pJH8fIFCiXHy0LaccrM3tWLdDadVhfaXFFUGqY5M.jpg",
      description: "Build your next coin startup"
    },
    {
      id: 3,
      title: "Banking Crypto",
      image: "https://zullkit-backend.demo.belajarkoding.com//storage/gallery/PciSvQHy1daoAfmaec02aTRabm8Bwubm9NYlxoiR.jpg",
      description: "Build your next coin startup"
    },
    ])
</script>

<template>
  <div class="container px-4 mx-auto my-16 md:px-12">
      <h2 class="mb-4 text-xl font-medium md:mb-0 md:text-lg">New Items</h2>
      <div class="flex flex-wrap -mx-1 lg:-mx-4">

        <ItemCard
          v-for="item in items"
          :key="item.id"
          :id="item.id"
          :image="item.image"
          :title="item.title"
          :description="item.description"
        />

        </div>
    </div>
</template>

<style lang="scss" scoped>

</style>