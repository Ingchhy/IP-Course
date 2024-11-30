<template>
  <div id="app">
    <div><category-component :manyCategorys="CategoryData"  class="component" /></div>
    <div><promotion-component :manyPromotions="PromotionData"
      class="component-1" /></div>
  </div>
</template>
<script>
import ButtonComponent from '../components/ButtonComponent.vue';
import PromotionComponent from '../components/PromotionComponent.vue';
import CategoryComponent from '../components/CategoryComponent.vue';
import srewberry from '@/assets/srewberry.jpg';
import avacado from '@/assets/avocado.png';
import vegetables from '@/assets/vegetables.png';


import apple from '@/assets/apple.png';
import kiki from '@/assets/kiwi.png'
import cabbage from '@/assets/cabbage.png'
import cake from '@/assets/cake.png'
import orange from '@/assets/headphone.png'
import broccoli from '@/assets/broccoli.png'  
import sandwich from '@/assets/sandwich.png'
import banana from '@/assets/banana.png'
import cherry from '@/assets/cherry.png'
import custardapple from '@/assets/custardapple.png'

export default {
  name: "App",
  components: {
    ButtonComponent,
    PromotionComponent,
    CategoryComponent
  },
  data() {
    return {
      PromotionData: [
        { names: 'Enjoy your day with the best drink', color: 'pink', url: srewberry, buttonColor:"red" },
        { names: 'Enjoy your day with the best fruit', color: 'lightyellow', url: avacado,buttonColor: "green" },
        { names: 'Enjoy your day with the best fresh vegetable', color: 'lightgreen', url: vegetables,buttonColor: "black" }
      ],
      CategoryData: [ 
        { lightColor:"#ff9999", name: 'apple', url: apple, des: "20 items"}, 
        { lightColor: "#99ff99", name: 'kiwi', url: kiki, des: "14 items" },
        { lightColor: "#ffff99", name: 'cabbage', url: cabbage, des: "17 items"}, 
        { lightColor: "#9999ff", name: 'cake', url: cake, des: "12 items" },
        { lightColor: "#ffcc99", name: 'custand', url: custardapple, des: "13 items"},
        { lightColor: "#cc99ff", name: 'headphone', url: orange, des: "11 items" }, 
        { lightColor: "#ff99cc", name: 'broccoli', url: broccoli, des: "15 items" }, 
        { lightColor: "#99ffff", name: 'sandwich', url: sandwich, des: "14 items" },  
        { lightColor: "#d2b48c", name: 'banana', url: banana, des: "24 items" }, 
        { lightColor: "#ffd700", name: 'cherry', url: cherry, des: "25 items" } 
      ]
    };
  }

};


</script>

<style scoped>

#app {
  display: flex;
  flex-direction: row;
  justify-content: center; 
  align-items: center; 
  background-color: #f5f5f5;
}
.component {
  margin-top: 200px;
}
</style>
<!-- <template>
  <div id="app">
  <div class="container">
    <MenuComponent  class="component-3" />
    <category-component :manyCategorys="categories" class="component" />
    <promotion-component :manyPromotions="promotions" class="component-1" />
    <MenuComponent  class="component-3" />
    <ProductComponent  :ManyProducts = "products" class="component-2" />
  </div>
  </div>
</template>
<script>
import { mapState } from 'pinia';
import { useProductStore } from './stores/index'; 
import { onMounted, computed } from 'vue';
import ProductComponent from './components/ProductComponent.vue'
import MenuComponent from './components/MenuComponent.vue'
import Category from './components/CategoryComponent.vue'
import Promotion from './components/PromotionComponent.vue'

export default {
  name: "App",
  setup() {
    const productStore = useProductStore();
    onMounted(() => {

      productStore.fetchCategories();
      productStore.fetchPromotions();
      productStore.fetchProducts();
    });
    // Dynamically map store data using mapState
    const categories = computed(() => productStore.categories);  
    const promotions = computed(() => productStore.promotions);
    const products = computed(() => productStore.products);

    return {
      categories,
      promotions,
      products,
      
    };
  },
  components: {
    MenuComponent,
    ProductComponent,
    Category,
    Promotion
  },
  computed: {
    ...mapState(useProductStore, {
      categories: 'categories', 
      promotions: 'promotions', 
      products: 'products',
    }),
  },
};
</script>

<style scoped>
#app {
  width: 100%;
  margin: 0 auto;
  font-family: Arial, sans-serif;
}
.container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 20px;
  padding: 20px;
}
.menu-bar {
  background-color: #f8f8f8;
  border: 1px solid #ddd;
  padding: 15px;
  text-align: center;
}
.featured-categories {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  justify-content: space-between;
}

.categories {
  flex: 1 1 calc(25% - 10px);
  border: 1px solid #ddd;
  text-align: center;
  padding: 10px;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}
.promotions-section {
  display: flex;
  gap: 15px;
  justify-content: space-between;
}

.promotion-card {
  flex: 1 1 calc(33% - 15px);
  border: 1px solid #ddd;
  padding: 15px;
  border-radius: 10px;
  background-color: #fefefe;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  text-align: center;
}

/* Popular Products Section */
.popular-products {
  margin-top: 20px;
}

.popular-products h2 {
  margin-bottom: 15px;
  font-size: 24px;
  color: #333;
}

.product-list {
  display: flex;
  flex-wrap: wrap;
  gap: 15px;
}

.product-list > * {
  flex: 1 1 calc(20% - 15px);
  background-color: #fff;
  border: 1px solid #ddd;
  padding: 10px;
  text-align: center;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.product-list img {
  max-width: 100%;
  border-radius: 4px;
}

/* Responsive Design */
@media screen and (max-width: 768px) {
  .categories, .promotion-card, .product-list > * {
    flex: 1 1 calc(50% - 10px);
  }
}

@media screen and (max-width: 480px) {
  .categories, .promotion-card, .product-list > * {
    flex: 1 1 100%;
  }
}
</style> -->