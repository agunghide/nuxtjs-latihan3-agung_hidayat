<template>
  <div class="main-content">
    <h1 class="text-3xl font-bold text-green-500 text-center">
      {{ categoryName }}
    </h1>
  </div>
</template>

<script>
export default {
    data() {
        return {
            categories: [
                {name: "Wisata Alam", slug: 'wisata-alam'},
                {name: "Wisata Buatan", slug: 'wisata-buatan'},
            ]
        }
    },
    computed:{
        categoryName(){
            var data = this.categories.find((item) => {
                return item.slug == this.$route.params.slug
            })
            return data.name
        }
    }
}
</script>
