<template> 
       <v-layout row wrap>              
              
              <v-flex xs12 sm6 lg2 v-for="(product,index) in products" :key="index">
                <v-card class="overlay_container">
                  <v-img :src="product.image" aspect-ratio="1"></v-img>

                  <v-card-title >
                    <div style="width:100%;" class="text-xs-center">
                      <h3 class="headline text-xs-center grey--text text--darken-3">{{product.name}}</h3>
                      <h4 class="grey--text text--darken-3">${{product.price}}</h4>                                           
                    </div>
                  </v-card-title> 
                  
                  <v-card class="overlay">
                      <h1 style="vertical-align: middle;">Add to shopping bag</h1>
                      <v-list class="details">
                      <v-list-tile-action>
                          <v-btn  v-on:click.stop="dialog = true" >Details</v-btn>
                      </v-list-tile-action>
                      <v-list-tile-action>
                          <v-btn color="primary" @click="addToCart(product)">Add To Cart</v-btn>
                      </v-list-tile-action>
                      </v-list>
                  </v-card>        
                </v-card>                
              </v-flex>

              <!-------modal_details--------->
        
              <v-dialog v-model="dialog"  transition="dialog-bottom-transition" width="80%">
                      
                <v-card xs12 sm12>
                  <v-toolbar dark class="primary" height="40px">
                  <v-spacer></v-spacer>
                    <v-btn  icon @click.native="dialog = false" dark>
                      <v-icon >close</v-icon>
                    </v-btn>
                  </v-toolbar>

                  <v-container>
                  <v-layout row wrap class="flex_box">
                    <v-flex xs12 sm12 md6 class="flex_item">
                      <v-card>
                        <v-img :src="require('@/assets/images/tshirt.jpg')" aspect-ratio="1"></v-img>
                        </v-card>
                      </v-flex>
                      
                      <v-flex xs12 sm12 md6 class="flex_item">
                        <v-card class="products_detail">
                            <v-card-text>
                              <h4 class="display-2 grey--text text--darken-2">code no:1243</h4>
                              <h4 class=" headline grey--text text--darken-2 my-3">$1200</h4>
                              <p class="my-3">
                                  One of the world’s oldest watchmakers, founded by Jules-Louis Audemars and
                                  Edward-Auguste Piguet, its watch signify the pinnacle of bold elegance and excellence
                                    in design. Audemars Piguet is still owned by its founding families and is recognised
                                    worldwide for creating luxurious Swiss watches.
                                  Quantity
                                  Category: Audemars Piguet	
                                </p>
                            </v-card-text>
                            
                            <v-layout row wrap class="mb-1" style="background:#efeded;padding:0!important;">
                            <v-flex xs12 sm6>
                              <v-select :items="itemz" label="Select" solo></v-select>
                            </v-flex>
                            <v-flex xs12 sm6>
                              <v-btn color="info">ADD TO CART</v-btn>
                              </v-flex>
                            </v-layout>
                            <v-card-title  style="background:#efeded;">
                                <p class="subheading blue--text text--darken-3 py-0 px-2">Category:T-shirt</p>
                            </v-card-title>
                        </v-card>
                      </v-flex>

                    </v-layout>
                  </v-container>
                </v-card>

              </v-dialog>

    </v-layout>


            
</template>

<script>
export default {
    data() {
    return {
      dialog: false,
      dialog1: false,
      drawer_left: null,
      drawer: null,
      drawer:false, 
      itemz:[],
     
    } 
  },
  props:['products'],
  methods:{
     addToCart(product){
        this.$emit('newItemAdded', product);
     }
  },
}
</script>

<style>

</style>
