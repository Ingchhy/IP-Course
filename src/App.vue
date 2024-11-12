<template>
  <div id="app">
    <div><category-component :manyCategorys="CategoryData"  class="component" /></div>
    <div><promotion-component :manyPromotions="PromotionData"
      class="component-1" /></div>
  </div>
</template>
<script>
import ButtonComponent from './components/ButtonComponent.vue';
import PromotionComponent from './components/PromotionComponent.vue';
import CategoryComponent from './components/CategoryComponent.vue';
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
        { lightColor:"#ff9999", name: 'apple', url: apple, des: "18 items"}, 
        { lightColor: "#99ff99", name: 'kiwi', url: kiki, des: "14 items" },
        { lightColor: "#ffff99", name: 'cabbage', url: cabbage, des: "17 items"}, 
        { lightColor: "#9999ff", name: 'cake', url: cake, des: "12 items" },
        { lightColor: "#ffcc99", name: 'custand', url: custardapple, des: "13 items"},
        { lightColor: "#cc99ff", name: 'headphone', url: orange, des: "10 items" }, 
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