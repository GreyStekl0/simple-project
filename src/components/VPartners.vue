<script setup>
const partners =[
  {
    img: {
      src: "/hahnemuehle.png",
      alt: "hahnemuehle"
    }
  },
  {
    img: {
      src: "/canson.png",
      alt: "canson"
    }
  },
  {
    img: {
      src: "/royal-talens.png",
      alt: "royal talens"
    }
  },
  {
    img: {
      src: "/fabriano.png",
      alt: "fabriano"
    }
  }
]

</script>

<template>
  <section class="partners">
    <div class="container">
      <div class="row">
        <div class="partners__card col-3"
             v-for="(item,index) in partners"
             :key="index">
          <img :src="item.img.src" :alt="item.img.alt">
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>

</style>