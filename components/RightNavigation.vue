<template> 

<v-content>
    <v-btn small @click.stop="drawer = !drawer" class="shop_card_section">
        <div class="shop_card">
            <v-icon>add_shopping_cart</v-icon>
            <h5>1 items</h5>
            <p style="">$00</p>
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
                <v-list-tile-title>Shop $300 more and save $20<span class="right">$50</span></v-list-tile-title>
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
               
            <!---------------------Your_order------------------------------------>
            <v-flex class="xs12 d-flex item_list">                
                <v-card-text flat class="quantity grey--text text--darken-2">
                    <v-icon small style="cursor: pointer;">expand_less</v-icon>
                    <p>10</p>
                    <v-icon small style="cursor: pointer;">expand_more</v-icon>
                </v-card-text>
                
                <v-card-text flat class="image">
                    <v-img :src="require('@/assets/images/tshirt.jpg')"></v-img>
                </v-card-text>
                
                <v-card-text flat class="item_name grey--text text--darken-2">
                    <p>Blue pure cotton t-shirt</p>
                    <p>$19</p>
                </v-card-text>
                
                <v-card-text flat  class="item_price red--text text--darken-2">
                    <p>$944466</p>
                    <p><del style="color:black;">$19</del></p>
                </v-card-text>
                
                <v-card-text flat class="close">
                    <v-icon small style="cursor: pointer;">close</v-icon>
                </v-card-text>                
            </v-flex>
                
            </v-list>
           </v-flex> 
    </v-navigation-drawer>
</v-content>
       
        
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
  props: {
    source: String
  }
}
</script>

<style>

</style>
