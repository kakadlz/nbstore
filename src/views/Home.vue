<template>
  <div class="home">

 
    <HeaderNBStore/>
    <HeroNBStore/>
    <ProductsNBStore/>
    <InstaNBStore/>
    <PartnerNBStore/>
    <FooterNBStore/>


   
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import HeaderNBStore from '@/components/HeaderNBStore.vue';
import HeroNBStore from '@/components/HeroNBStore.vue';
import ProductsNBStore from '@/components/ProductsNBStore.vue';
import InstaNBStore from '@/components/InstaNBStore.vue';
import PartnerNBStore from '@/components/PartnerNBStore.vue';
import FooterNBStore from '@/components/FooterNBStore.vue';


export default {
  name: 'Home',
  components: {
    // HelloWorld,
    HeaderNBStore,
    ProductsNBStore,
    HeroNBStore,
    InstaNBStore,
    PartnerNBStore,
    FooterNBStore,
  }
}
</script>
