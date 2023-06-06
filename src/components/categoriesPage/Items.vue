<script setup>
  import { ref } from 'vue';
  import ItemCard from '../homePage/items/ItemCard.vue';
  import axios from 'axios'
  import { onMounted } from 'vue';
  import { useRoute } from 'vue-router';

  const items = ref([])
  const category = ref({})
  const route = useRoute()
  console.log(route.params.id);

  async function getDataProduct(){
    try{
      const response = await axios.get("https://zullkit-backend.buildwithangga.id/api/categories?id="+ route.params.id +"&show_product=1")
      items.value = response.data.data.products
      category.value = response.data.data
    }catch(error){
      console.log(error);
    }
  }

  onMounted(() => {
    getDataProduct()
    console.log(items);
  })
</script>

<template>
  <div class="container px-4 mx-auto my-16 md:px-12">
      <h2 class="mb-4 text-xl font-medium md:mb-0 md:text-lg">{{ category.name }}</h2>
      <div class="flex flex-wrap -mx-1 lg:-mx-4">
        <ItemCard
          v-for="item in items"
          :key="item.id"
          :id="item.id"
          :image="item.thumbnails"
          :title="item.name"
          :description="item.subtitle"
        />
      </div>
    </div>
</template>