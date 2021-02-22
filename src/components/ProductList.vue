<template>
  <div class="product-list">
    <div class="flex top-information">
      <h1>Rašomieji stalai</h1>
      <search @search="searchProducts" />
    </div>

    <ul class="list-default flex">
      <li v-for="(product, index) in products" :key="index">
        <product-card
          :title="product.title"
          :price="product.price"
          :imgUrl="product.imgUrl"
          :count="product.count"
          @addToBasket="addToBasket(index)"
        />
      </li>
    </ul>
  </div>
</template>
<script>
import ProductCard from './ProductCard.vue';
import Search from './Search.vue';
export default {
  name: 'ProductList',
  components: { ProductCard, Search },
  data() {
    return {
      products: [
        {
          title: 'Skarsta',
          price: 169,
          imgUrl:
            'https://d2rbyiw1vv51io.cloudfront.net/web/ikea4/images/701/0770108_PE755457_S5.jpg',
          count: 5,
        },
        {
          title: 'Bekant',
          price: 268,
          imgUrl:
            'https://d2rbyiw1vv51io.cloudfront.net/web/ikea4/images/379/0937940_PE793886_S4.jpg',
          count: 7,
        },
        {
          title: 'Bekant',
          price: 229,
          imgUrl:
            'https://d2rbyiw1vv51io.cloudfront.net/web/ikea4/images/364/0736451_PE740560_S4.jpg',
          count: 2,
        },
        {
          title: 'Micke',
          price: 69,
          imgUrl:
            'https://d2rbyiw1vv51io.cloudfront.net/web/ikea4/images/360/0736018_PE740345_S4.jpg',
          count: 3,
        },
        {
          title: 'Skarsta',
          price: 169,
          imgUrl:
            'https://d2rbyiw1vv51io.cloudfront.net/web/ikea4/images/776/0777622_PE758666_S4.jpg',
          count: 6,
        },
      ],
    };
  },
  methods: {
    addToBasket(index) {
      console.log(index);
    },
    searchProducts(searchText) {
      console.log(searchText);
    },
  },
};
</script>
<style>
.product-list li {
  display: inline-block;
  width: 20%;
}
</style>
