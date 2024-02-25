<script setup>
const items = [
  {
    img: {
      src:"/package.png",
      alt:"package",
    },
    name: "Упаковка",
    text: 'Сделано из крафт-бумаги или плотного картона. Упаковки имеют различные формы и расцветки, изготовим форму под заказ.',
    circulation: "50"
  },
  {
    img: {
      src:"/bags.png",
      alt:"bags",
    },
    name: "Пакеты",
    text: 'С прямоугольным дном. От 10см до 60см по высоте. Материалы: картон, крафт-бумага. Различные расцветки и дизайн.',
    circulation: "200"
  },
  {
    img: {
      src:"/cases.png",
      alt:"cases",
    },
    name: "Кейсы",
    text: 'Подойдет для документов и других бумаг. Различные расцветки, размеры и плотность. Материал: прессованная бумага.',
    circulation: "30"
  },
  {
    img: {
      src:"/other_products.png",
      alt:"other products",
    },
    name: "Другие изделия",
    text: 'Нестандартные упаковки, кейсы и другие изделия различных размеров и конфигураций. Изготовим в кратчайшие сроки.',
    circulation: "100"
  },
]
</script>

<template>
  <section class="items">
    <div class="container">
      <div class="row">
        <div class="items__card col-3"
             v-for="(item,index) in items"
             :key="index">
          <img class="items__card-img" :src="item.img.src" :alt="item.img.alt">
          <h2>{{item.name}}</h2>
          <p class="circulation">Тираж от {{item.circulation}} штук </p>
          <p class="items__card-text">{{item.text}}</p>
          <button>Подробнее <svg width="21" height="15" viewBox="0 0 21 15" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M20.7071 8.20711C21.0976 7.81658 21.0976 7.18342 20.7071 6.79289L14.3431 0.428932C13.9526 0.0384078 13.3195 0.0384078 12.9289 0.428932C12.5384 0.819457 12.5384 1.45262 12.9289 1.84315L18.5858 7.5L12.9289 13.1569C12.5384 13.5474 12.5384 14.1805 12.9289 14.5711C13.3195 14.9616 13.9526 14.9616 14.3431 14.5711L20.7071 8.20711ZM0 8.5H20V6.5H0V8.5Z" fill="currentColor"/>
          </svg></button>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>

</style>