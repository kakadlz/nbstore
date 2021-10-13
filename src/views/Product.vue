<template>
  <div class="product">

 
    <HeaderNBStore/>
    <BreacrumbNBStore/>
    <Productshop/>
    <Relatedproduct/>
    <FooterNBStore/>


   
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import HeaderNBStore from '@/components/HeaderNBStore.vue';
import BreacrumbNBStore from '@/components/BreacrumbNBStore.vue';
import Productshop from '@/components/Product/Productshop.vue';
import Relatedproduct from '@/components/Product/Relatedproduct.vue';
import FooterNBStore from '@/components/FooterNBStore.vue';


export default {
  name: 'Product',
  components: {
    HeaderNBStore,
    FooterNBStore,
    BreacrumbNBStore,
    Productshop,
    Relatedproduct,
  }
}
</script>
