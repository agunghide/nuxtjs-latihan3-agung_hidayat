<template>
  <div class="main-content text-center flex flex-col items-center">
    <div class="container grid grid-cols-3 gap-3 mx-auto">
      <div class="w-full rounded overflow-hidden" v-for="(image, index) in images" :key="index">
          <img 
            class="image-animation"
            :src="require(`@/assets/images/${image}`)"
            alt="image">
      </div>
  </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      images: [
        '1.jpg',
        '2.jpg',
        '3.jpg',
        '4.jpg',
        '5.jpg',
        '6.jpg',
      ]
    }
  },
}
</script>
