<template> 
    <v-layout row wrap>
                <v-btn small @click.stop="drawer = !drawer" class="shop_card_section">
                    <div class="shop_card">
                        <v-icon>add_shopping_cart</v-icon>
                        <h5>{{totalQuantity}} items</h5>
                        <p>${{totalPrice}}</p>
                    </div>
                </v-btn>
              
                <v-navigation-drawer
                          v-model="drawer"
                          fixed
                          right
                          clipped
                          app class="close_div">
              
                        <v-flex xs12>
                          <!--------navigation_top--------------->
                          <v-list dense style="margin:0!important;padding:1px 0 0!important;">
                             <v-list-tile class="navigation_card_quantity grey darken-5 white--text">
                                <v-list-tile-action>
                                  <v-icon class="white--text">shopping_cart</v-icon>
                                </v-list-tile-action>
                                
                                <v-list-tile-title>
                                    0 ITEMS
                                </v-list-tile-title>
                                <v-btn  class="grey--text text--darken-2" small @click.stop="drawer = !drawer"><span>close</span></v-btn>
                            </v-list-tile>
                        </v-list>
                          
                        <!-------------------------->
                        <v-list dense   class="right_navigation" style="margin:0!important;padding:0!important;">
                            <v-list-tile  class=" px-3 blue darken-3  white--text">
                              <v-list-tile-content>
                                <v-list-tile-title>Shop $300 more and save $20<span class="right">$50</span></v-list-tile-title>
                              </v-list-tile-content>
                            </v-list-tile>
                            
                             <v-flex xs12>
                              <v-img
                                :src="require('@/assets/images/bag.png')"
                                aspect-ratio="1" contain   
                                 style="width:70%;margin:15% auto;border-radius:50%;background:#9E9E9E;"
                              ></v-img>
                            </v-flex>
                            
                             <v-list-tile  class="px-3 grey--text text--darken-2">
                                <span class="text-xs-center title" style="width:100%;">
                                    Your shopping bag is empty.
                                </span>
                            </v-list-tile>
                            
                            <v-list-tile  class="px-3 grey--text text--darken-2">
                                <span class="text-xs-center  headline mt-3" style="width:100%;font-weight: bold;">
                                    Phone:00467388
                                </span>
                            </v-list-tile>
                        </v-list>
                          
                        <!---------------------------------->
                          
                        <v-list dense   class="right_navigation1" style="margin:0!important;padding:0!important;">
                        <v-list-tile  class=" px-1 blue darken-3  white--text">
                            <v-list-tile-content>
                            <v-list-tile-title>Shop $300 more and save $20<span class="right">${{totalPrice}}</span></v-list-tile-title>
                            </v-list-tile-content>
                        </v-list-tile>
                        
                        <v-list-tile class=" px-1 grey lighten-2 grey--text text--darken-2">
                            <v-list-tile-action>
                                <v-icon class="grey--text text--darken-2">local_shipping</v-icon>
                            </v-list-tile-action>
                            
                            <v-list-tile-title>
                                <p class="body-2">EXPRESS DELIVERY</p>
                            </v-list-tile-title>
                        </v-list-tile>
                           
                        <!---------------------Cart------------------------------------>

                        <v-flex class="xs12 d-flex item_list" v-for="(product, index) in products" :key="index">                
                            <v-card-text flat class="quantity grey--text text--darken-2">
                                <v-icon small style="cursor: pointer;">expand_less</v-icon>
                                <p>1</p>
                                <v-icon small style="cursor: pointer;">expand_more</v-icon>
                            </v-card-text>
                            
                            <v-card-text flat class="image">
                                <v-img :src="product.image" aspect-ratio="1"></v-img>
                            </v-card-text>
                            
                            <v-card-text flat class="item_name grey--text text--darken-2">
                                <p>{{product.name}}</p>
                                <p>${{product.price}}</p>
                            </v-card-text>
                            
                            <v-card-text flat  class="item_price black--text text--darken-2">
                                <p>${{product.price}}</p>                                
                            </v-card-text>
                            
                            <v-card-text flat class="close">
                                <v-icon @click="removeProduct(index)" small style="cursor: pointer;">close</v-icon>
                            </v-card-text>                
                        </v-flex>
                            
                        </v-list>
                       </v-flex> 
                  </v-navigation-drawer>


                  <!---------Feature----------------------->
                  <v-content>
                        <v-container>
                          <v-layout row wrap class="flex_box feature">
                              <v-flex xs12 sm4 class="flex_item ">
                                <v-card class="border_transition ">
                                  <div class="background_transition">
                                  <div class="text-xs-center">
                                    <v-icon x-large class="blue--text  darken-3">local_shipping</v-icon>
                                  </div>
                                  <v-card-title primary-title>
                                    <div class="headline text-xs-center">FREE DELIVERY FROM $200</div>
                                  </v-card-title>
                                  <v-card-text>
                                    <p > Manage and invoice projects with the powerful project management feature. Track expenses and time spent on tasks and bill your customers.</p> 
                                  </v-card-text>
                                  </div>
                                </v-card>
                              </v-flex>
                              <v-flex xs12 sm4 class="flex_item">
                                <v-card class="border_transition">
                                  <div class="background_transition">
                                  <div class="text-xs-center">
                                    <v-icon x-large class="blue--text  darken-3">money_off</v-icon>
                                  </div>
                                  <v-card-title primary-title>
                                    <div class="headline text-xs-center">MONEY BACK GURANTEE</div>
                                  </v-card-title>
                                  <v-card-text>
                                    Build professional and great looking invoices. Attach files and send directly to your clients including the invoice PDF. 
                                  </v-card-text>
                                  </div>
                                </v-card>
                              </v-flex>
                              <v-flex xs12 sm4 class="flex_item">
                                <v-card class="border_transition">
                                  <div class="background_transition">
                                  <div class="text-xs-center">
                                    <v-icon x-large class="blue--text  darken-3">check_circle</v-icon>
                                  </div>
                                  <v-card-title primary-title>
                                    <div class="headline text-xs-center">AUTHENTICITY 100% GURANTED</div>
                                  </v-card-title>
                                  <v-card-text>
                                    Create estimate within a minute. Sent to your customers and wait to accept. Ability to auto convert the estimate to invoice after customer accept. 
                                  </v-card-text>
                                  </div>
                                </v-card>
                              </v-flex>
                            </v-layout>
                          </v-container>
                      </v-content>         
    </v-layout>         
</template>

<script>
export default {
    data() {
    return {
      dialog: false,
      dialog1: false,      
      drawer: null,
      drawer:false,  
    }   
  },
  props: ['products'],
  computed:{
    totalPrice(){
      var total=0;
      this.products.forEach(product => {
        total += parseFloat(product.price)
      });
      return total.toFixed(2);
    },
    totalQuantity(){
      var total=0;
      this.products.forEach(product => {
        total += parseFloat(product.quantity)
      });
      return total;
    }
  },
  methods:{
    removeProduct(index){      
      this.$emit('productRemoved', index)
    }
  }
  
  
}
</script>

