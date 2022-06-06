<template>
  <Header/>
  <FirstScreen/>
  <BooksSlider :sliderItems="sliderItems" @add-basket="addToBasket"/>
</template>

<script>
import Header from "@/components/Header";
import FirstScreen from "@/components/FirstScreen"
import BooksSlider from "@/components/BooksSlider";

export default {
  name: 'HomeView',
  data() {
    return {
      sliderItems: [
        {
          id: 1,
          name: 'Ж. Верн, “Двадцать тысяч лье под водой”',
          img: require('@/assets/img/book-1.png'),
          theme: 'Приключения',
          price: 168,
        },
        {
          id: 2,
          name: 'Н. Кун, “Легенды и мифы Древней Греции”',
          img: require('@/assets/img/book-2.png'),
          theme: 'Эпос и фольклор',
          price: 174,
        },
        {
          id: 3,
          name: 'Гомер, “Илиада”',
          img: require('@/assets/img/book-3.png'),
          theme: 'Эпос и фольклор',
          price: 155,
        },
        {
          id: 1,
          name: 'Ж. Верн, “Двадцать тысяч лье под водой”',
          img: require('@/assets/img/book-1.png'),
          theme: 'Приключения',
          price: 168,
        },
        {
          id: 2,
          name: 'Н. Кун, “Легенды и мифы Древней Греции”',
          img: require('@/assets/img/book-2.png'),
          theme: 'Эпос и фольклор',
          price: 174,
        },
        {
          id: 3,
          name: 'Гомер, “Илиада”',
          img: require('@/assets/img/book-3.png'),
          theme: 'Эпос и фольклор',
          price: 155,
        },],
      basketItems: [],
    }
  },
  methods: {
    addToBasket(id) {
      let item = this.sliderItems.find(el => el.id = id);
      this.basketItems.push(item)
    }
  },
  components: {
    Header, FirstScreen, BooksSlider
  }
}
</script>
