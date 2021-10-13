<template>
  <div class="shopping">

 
    <HeaderNBStore/>
    <BreacrumbNBStore/>
    <ShoppingCart/>


   
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import HeaderNBStore from '@/components/HeaderNBStore.vue';
import BreacrumbNBStore from '@/components/BreacrumbNBStore.vue';
import ShoppingCart from '@/components/ShoppingCart/ShoppingCart.vue';


export default {
  name: 'cart',
  components: {
    HeaderNBStore,
    BreacrumbNBStore,
    ShoppingCart,
  }
}
</script>
