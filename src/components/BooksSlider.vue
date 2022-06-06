<template>
  <section class="books-slider">
    <div class="container">
      <h2 class="books-slider__title">Горячие новинки</h2>
      <carousel :settings="settings">
        <slide v-for="slide in sliderItems" :key="slide.id">
          <div class="books-slider__item">
            <img :src="slide.img" alt="">
            <div class="title">{{ slide.name }}</div>
            <div class="theme">
              {{ slide.theme }}
            </div>
            <div class="bottom">
              <span class="price">{{ slide.price }} р.</span>
              <button class="btn btn-black" @click="addItems(slide.id)">Купить</button>
            </div>
          </div>
        </slide>

        <template #addons>
          <div class="books-slider__navigation">
            <navigation/>
            <pagination/>
          </div>
        </template>
      </carousel>
    </div>
  </section>
</template>

<script>
import {Carousel, Navigation, Pagination, Slide} from 'vue3-carousel';

export default {
  emits: ['addToBasket'],
  props: {
    sliderItems: Array,
  },
  data() {
    return {
      settings: {
        itemsToShow: 3,
        itemsToScroll: 1,
        wrapAround: true,
      }
    }
  },
  methods: {
    addItems(id) {
      this.$emit('addBasket',id)
    }
  },
  name: "BooksSlider",
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
  }
}
</script>

<style scoped>

</style>
