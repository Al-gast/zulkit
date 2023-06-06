<script setup>
  defineProps({
    thumbnails: String,
    galleries: Array
  })
</script>

<template>
  <section id="gallery">
    <img
    :src="thumbnails" 
    alt="" 
    class="w-full mt-6 rounded-2xl max-h-fit">
    <div class="grid grid-cols-4 gap-4 mt-4">
      <template v-for="gallery in galleries" :key="gallery.id">
        <div @click="thumbnails = gallery.url" class="overflow-hidden cursor-pointer rounded-2xl" :class="{'ring-2 ring-indigo-500':
        thumbnails === gallery.url}">
          <img 
          :src="gallery.url" 
          class="w-full" alt="">
        </div>
      </template>
    </div>
  </section>
</template>

<style lang="scss" scoped>

</style>