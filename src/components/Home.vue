<template>
  <div class="">
        <Menu/>
    
        <div class="container">
            <div class="row">
            
                <div class="col-md-3 col-sm-4" v-for="product in products">
                <router-link v-bind:to="`product/` + product._id" class=""> 
                    <div href="" class="card card-product-grid" style="border: 0;">
                        
                        <router-link v-bind:to="`product/` + product._id" class="img-wrap p-2"> 
                            <img v-bind:src="`http://localhost:8081/public/products/`+ product.images[0]" class="img-fluid d-block" style="margin-left: auto; margin-right: auto; display: block;"> 
                        </router-link>
                        
                        <figcaption class="info-wrap text-center">
                            <label title="">
                                <router-link v-bind:to="`product/` + product._id" class="title">{{product.product_name.substring(0, 25) + "..."}}</router-link>	
                            </label>
                            <div class="price mt-1">RD$ {{product.product_price.toFixed(2).replace(/\d(?=(\d{3})+\.)/g, '$&,') }}</div> <!-- price-wrap.// -->
                        </figcaption>
                    </div>
                </router-link> 
                </div> <!-- col.// -->

            </div>
        </div>
        <Footer/>
  </div>
</template>

<script>
import Footer from "./Footer.vue"
import Menu from "./Menu.vue"

export default {

  
  name: 'Home',
  components: {
    Footer,
    Menu
  },

  data () {
    return {
        products: []
    }
  },

  created(){
    this.getProducts()
  },

  methods: {
      getProducts(){
          fetch('http://localhost:8081/')
          .then(res => res.json())
          .then(data => {
              this.products = data
          })
      }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.card *, .card{
    border: none !important;
}

.card{
    box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
    
}

.card input, .card textarea, .card select{
    box-shadow: rgba(100, 100, 111, 0.1) 0px 2px 29px 0px;

}

.card .btn{
    width: 100%;
}
</style>
