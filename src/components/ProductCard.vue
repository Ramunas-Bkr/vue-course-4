<template>
  <div class="product-card">
    <img :src="imgUrl" alt="no_image" />
    <div class="product-card__info">
      <h2>Stalas {{ title }}</h2>
      <p class="price">Kaina {{ price }} &euro;</p>
      <p class="count">Sandėlyje turime {{ count }} vnt</p>
      <button @click="addToBasket">Pridėti į krepšelį</button>
    </div>
  </div>
</template>
<script>
export default {
  name: 'ProductCard',
  props: {
    title: {
      type: String,
      validator(value) {
        return value.length < 20;
      },
    },
    price: {
      type: Number,
      required: true,
    },
    imgUrl: {
      type: String,
      default:
        'https://us.123rf.com/450wm/barbulat/barbulat1809/barbulat180900094/109243289-stock-vector-no-image-available-sign.jpg?ver=6',
    },
    count: {
      type: Number,
      default: 0,
    },
  },
  methods: {
    addToBasket() {
      this.$emit('addToBasket');
    },
  },
};
</script>
<style>
.product-card {
  margin: 5px;
  border: 1px solid rgb(211, 211, 211);
  padding: 20px 15px;
  text-align: center;
}
.product-card img {
  width: 80%;
  height: auto;
}
.product-card__info {
  margin-top: 20px;
}
</style>
