<template>
    <div>

            <!-- Product Shop Section Begin -->
            <section class="product-shop spad page-details">
                <div class="container">
                    <div class="row">
                        <div class="col-lg-12">
                            <div class="row">
                                <div class="col-lg-6">
                                    <div class="product-pic-zoom">
                                        <img class="product-big-img" :src="gambar_default" alt="" />
                                    </div>
                                    <div class="product-thumbs" v-if="productDetails.product_galleries.length>0">
                                        <carousel class="product-thumbs-track ps-slider" :items="3" :nav="false" :autoplay="false"  :loop="false" :dots="false">
                                            <div v-for="ss in productDetails.product_galleries" :key="ss.id" class="pt " @click="changeImage(ss.photo)" :class="ss.photo== gambar_default ? 'active' : '' ">
                                                <img :src="ss.photo" alt="" />
                                            </div>

                                            <!-- <div class="pt"  @click="changeImage(thumbs[1])" :class="thumbs[1]== gambar_default ? 'active' : '' ">
                                                <img src="img/nb/nb2.jpg" alt="" />
                                            </div>

                                            <div class="pt"  @click="changeImage(thumbs[2])" :class="thumbs[2]== gambar_default ? 'active' : '' ">
                                                <img src="img/nb/nb3.jpg" alt="" />
                                            </div>

                                            <div class="pt" @click="changeImage(thumbs[3])" :class="thumbs[3]== gambar_default ? 'active' : '' ">
                                                <img src="img/nb/nb4.jpg" alt="" />
                                            </div> -->
                                        </carousel>
                                    </div>
                                </div>
                                <div class="col-lg-6">
                                    <div class="product-details">
                                        <div class="pd-title  text-left">
                                            <span>{{productDetails.type}}</span>
                                            <h3>{{productDetails.name}}</h3>
                                        </div>
                                        <div class="pd-desc  text-left">
                                            <p>{{productDetails.description}}</p>
                                            <h4>${{productDetails.price}}</h4>
                                        </div>
                                        <div class="quantity">
                                            <router-link to="/cart" class="primary-btn pd-cart">Add To Cart</router-link>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </section>
            <!-- Product Shop Section End -->
    </div>
</template>

<script>
import carousel from 'vue-owl-carousel';
import axios from 'axios';
export default {
    name : "Productshop",
  components: {
    carousel
  },
  data(){
      return{
          gambar_default:"img/nb/nb1.jpg",
          thumbs:[
              "img/nb/nb1.jpg",
              "img/nb/nb2.jpg",
              "img/nb/nb3.jpg",
              "img/nb/nb4.jpg",
          ],
          productDetails:[]
      }
  },
  methods:{
      changeImage(urlImage){
          this.gambar_default=urlImage;
          //eslint-disable-next-line no-console
        //   console.log(this.id); 
      },
  setDataPictures(data){
      this.productDetails=data;
      this.gambar_default=data.product_galleries[0].photo;

  },

  },
  
  mounted(){
      axios
      .get("http://127.0.0.1:8000/api/products",{
          params:{
            id:this.$route.params.id
          }
      })
      .then(res=>(this.setDataPictures(res.data.data)))
      .catch(err=>console.log(err));
  }
}
</script>
<style scoped>
.product-thumbs .pt {
    margin-right: 10px;
}
</style>