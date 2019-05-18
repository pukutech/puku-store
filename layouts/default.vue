<template>
  <v-app id="inspire">
   <!-----left_navigation_drawer--->
    <Navbar/>
    
    <!-------Products------------>       

    <v-content>          
      <v-container fill-height grid-list-lg>
          <Products @newItemAdded="addCartItem" :products='products' />
      </v-container>
    </v-content>

    <!---Right_navigation_drawer----> 
    <RightNavigation @productRemoved="removeProduct" :products='cart' />      
    
    <!-------Modal---------->
    <Modal />
    
   
  </v-app>
</template>

<script>
import RightNavigation from '~/components/RightNavigation.vue'
import Products from '~/components/Products.vue'
import Modal from '~/components/Modal.vue'
import Navbar from '~/components/Navbar.vue'
export default {
components:{
 RightNavigation,Products,Modal,Navbar
},
data() {
return {     
  dialog: false,
  dialog1: false,
  drawer_left: null,
  drawer: null,
  drawer:false, 
  itemz:[],
  items: [
    { icon: 'contacts', text: 'Contacts' },
    { icon: 'history', text: 'Frequently contacted' },
    { icon: 'content_copy', text: 'Duplicates' },
    {
      icon: 'keyboard_arrow_up',
      'icon-alt': 'keyboard_arrow_down',
      text: 'Labels',
      model: true,
      children: [
        { icon: 'add', text: 'Create label' }
      ]
    },
    {
      icon: 'keyboard_arrow_up',
      'icon-alt': 'keyboard_arrow_down',
      text: 'More',
      model: false,
      children: [
        { text: 'Import' },
        { text: 'Export' },
        { text: 'Print' },
        { text: 'Undo changes' },
        { text: 'Other contacts' }
      ]
    },
    { icon: 'settings', text: 'Settings' },
    { icon: 'chat_bubble', text: 'Send feedback' },
    { icon: 'help', text: 'Help' },
    { icon: 'phonelink', text: 'App downloads' },
    { icon: 'keyboard', text: 'Go to the old version' }
  ],
  products:[
    {name:"Buldozer Blue", quantity:1, price:"1.30", image:"https://shop.budspencerofficial.com/340-large_default/bud-spencer-bulldozer-63-t-shirt.jpg"},
    {name:"Visit Arakis", quantity:1, price:"2.30", image:"https://images-na.ssl-images-amazon.com/images/I/81tHrL6pNcL._UL1500_.jpg"},
    {name:"Khobsgol Lake", quantity:1, price:"3.30", image:"https://cdn.shopify.com/s/files/1/0660/7355/products/Royal_Enfield_Icing_On_A_Lake_T-Shirt_Lake_Blue_1_1400x.jpg?v=1537426243"},
    {name:"Buldozer White", quantity:1, price:"11.30", image:"https://shop.budspencerofficial.com/356-large_default/bud-spencer-bulldozer-63-grey-t-shirt.jpg"},
    {name:"Easily", quantity:1, price:"7.30", image:"https://cdn.shopify.com/s/files/1/1782/0735/products/DynamicImageHandler_0cf109d1-7cbd-4da2-88a2-88909a8dd993_1024x1024.jpg?v=1507277076"},
    {name:"Yellow Bull", quantity:1, price:"8.30", image:"https://image.spreadshirtmedia.net/image-server/v1/products/133248349/views/1,width=650,height=650,appearanceId=7,version=1478003241.jpg"},
    {name:"Heroes", quantity:1, price:"4.30", image:"https://shop.budspencerofficial.com/466-large_default/bud-spencer-old-school-heroes-white-girls-t-shirt.jpg"},
    {name:"Hello", quantity:1, price:"3.30", image:"https://m.media-amazon.com/images/I/B1qmQK-r4OS._CLa%7C2140,2000%7C718jTY4XCZL.png%7C0,0,2140,2000+0.0,0.0,2140.0,2000.0._UX522_.png"},
    {name:"Mucke", quantity:1, price:"21.30", image:"http://www.style3.de/ebay/860027_03.jpg"},
    {name:"Bomber", quantity:1, price:"9.30", image:"https://www.dhresource.com/0x0s/f2-albu-g8-M01-75-15-rBVaVFyUyCCABUvhAAFaJhUX7m8137.jpg/bomber-bud-spencer-jerry-cal-boxe-trash-pugilato.jpg"},
    {name:"Ramon", quantity:1, price:"4.30", image:"https://image.spreadshirtmedia.net/image-server/v1/products/107742338/views/2,width=650,height=650,appearanceId=1,version=1478003241.jpg"},
    {name:"Smile", quantity:1, price:"2.30", image:"https://www.terencebud.de/media/images/org/buddy-t-shirt-bud-spencer-orange.jpg"},
  ],
  cart:[]
}
},
methods:{
  addCartItem(product){
    this.cart.push(product);
  },
  removeProduct(index){
    this.cart.splice(index, 1)
  }
}

}
</script>


<style>
.header .theme--dark.v-text-field--solo-inverted.v-text-field--solo > .v-input__control > .v-input__slot {
background: rgba(255,255,255,0.16);
margin-top: 10px;
}
.right_navigation{
display:none;
}
 
.right_navigation  .v-list__tile__action {
min-width: 35px;
}
  
.navigation_card_quantity .v-list__tile__action {
display: flex;
justify-content: flex-start;
min-width: 35px;
}
.right_navigation1  .v-list__tile__action {
min-width: 35px;
}

.item_list{
height:auto;
border-bottom: 1px solid #E0E0E0;
padding:0;
}     
  
.v-card__text{
padding:0;
}
.item_list .quantity{
height: 70px;
width:10%; 
display: grid;
justify-items: center;
align-items: center;
text-align: center;
border-right: 1px solid #E0E0E0;
}
.item_list .quantity p{
margin:0;
}
  
.item_list .image{
height: 70px;
width:15%; 
display:flex;
justify-items: center;
align-items: center;
text-align: center;
}
  
.item_list .item_name{
height: 70px;
width:35%; 
padding:8px 2px;
display: grid;
justify-items: center;
align-items: center;
text-align: center;
}
.item_list .item_name p{
font-size: 12px;
margin-top:-15px;
}
.item_list .item_name p:nth-of-type(1){
margin-top:0px;
}
  
.item_list .item_price{
height: 70px;
width:20%; 
padding:8px 0px;
display: grid;
justify-items: center;
align-items: center;
text-align: center;
}

.item_list .item_price p{
margin-top:-15px;
}

.item_list .item_price p:nth-of-type(1){
margin-top:0px;
}

.item_list .close{
height: 70px;
width:3%; 
display: grid;
justify-items: center;
align-items: center;
text-align: center;
}
  
.item_list .close .v-icon{
margin-left: -5px;
}
  
.overlay{
position:absolute;
top:0;
width:100%;
height:100%;
opacity:0;
text-align:center;
background: rgb(0,0,0,.4)!important;
-webkit-transition: all 0.5s;
-moz-transition: all 0.5s;
-ms-transition: all 0.5s;
-o-transition: all 0.5s;
transition: all 0.5s;
}
  
.overlay h1{
margin-top: 40%;
color:#FFF;
padding-left:20%;
padding-right:20%;
}     
  
.overlay_container:hover .overlay{
opacity:1;
box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.5), 0 6px 20px 0 rgba(0, 0, 0, 0.39);
}
.shop_card_section{
color:white!important;
height:80px!important;
min-width:65px!important;
position:fixed!important;
right:0!important;
top:50%!important;
z-index:1!important;
background: RGB(49,120,200,.8)!important;
padding:0!important;  
}

.shop_card{
position:relative;
width:100%;
float:left;padding:0!important;
margin:0!important; 
}

.shop_card p{
position:absolute;
margin-bottom:0;
width:100%;
background: #FFF;
color:black;
}

.details{
position:absolute;
bottom:0;
left:0;
text-align:center;
width:100%;
margin:0;
padding: 0;
}

.details .v-btn{
width:100%;
}
  
.flex_box .v-card {
padding: 30px!important;
line-height: 22px;
}

.flex_box{
display:flex;
}

.flex_item{
flex:1;
display:flex;
flex-wrap:wrap;
flex-grow: 1;          
}

.flex_box .v-card{
padding:20px; 
width:100%;
}
  
.flex_item .headline{
width:100%;
margin-bottom:15px;
}
  
.flex_box .v-card__text {
padding: 0px;
}
  
.flex_box .v-card__title {
padding:10px 0 0;
}
  
.feature .headline{
font-size:18px!important;
font-weight: bold;
}  

.border_transition{
height:100%;
width:100%;
position:relative;
background:transparent;
outline:none;
border:none;
}

.border_transition:before{
position:absolute;
content:'';
height:0;
width:0;
border:1px solid transparent;
left:0;
top:0;
box-sizing:border-box;
}

.border_transition:hover:before{
height:100%;
width:100%;
border:1px solid #bbdefb;
border-left:none;
border-bottom:none;
transition:height 0.3s linear  0.3s,
width 0.3s linear ;        
}

.border_transition:after{
position:absolute;
content:'';
height:0;
width:0;
border:1px solid transparent;
top:0;
left:0;
box-sizing:border-box;
}	

.border_transition:hover:after{
height:100%;
width:100%;
border:1px solid #90caf9  ;
border-right:none;
border-top:none;
transition:height 0.3s linear,
width 0.3s linear 0.3s;
}

.background_transition:hover{
color:#9e9e9e!important;
}
.background_transition{
animation: change .1s 0.1s;    
}
  
@keyframes change {
0% { color:black;}
1% { color:black; }
}
  
.products_detail .v-card__actions {
padding: 0 20px;
margin:20px 0;
}
.products_detail .v-text-field>.v-input__control>.v-input__slot {
width: 40%!important;
margin: 7px 0 0!important;
}     
  
.products_detail p{
background:#efeded;
padding:20px;
}
.products_detail .v-text-field > .v-input__control > .v-input__slot {
width: 70% !important;
margin: 5px 0 0 8px!important;
}

.products_detail .v-text-field.v-text-field--solo .v-input__control {
max-height: 20px!important;
padding: 0;
}
.v-text-field.v-text-field--solo .v-input__control {
min-height: 38px!important;
padding: 0;
margin-bottom: 10px;
}
@media (max-width:599px){
.v-text-field.v-text-field--solo .v-input__control {
min-height: 38px!important;
padding: 0;
margin-bottom: 5px;
}
}
@media (max-width:420px){
.products_detail h4,.products_detail .my-3{
font-size: 20px!important;
margin-top:0!important;
padding:0 10px!important;
} 
.flex_box .v-card{
padding:0!important;  
}
.products_detail .v-card__text  p{
font-size:14px!important;
padding:10px!important;
}         
}
</style>