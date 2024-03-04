<script>

import axios from 'axios'
import {store} from './store.js'
import AppContent from './components/AppContent.vue'

export default{


  components:{
    AppContent
  },

    data(){
      return{
          
          images:[],
          images2:[],

          store,
      }
    },


    created() {
    
    
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0').then(res => {
       

        for(let i=0; i<res.data.data.length; i++ ){
          //console.log(res.data.data[i])
         // this.images.push( res.data.data[i].card_images[0].image_url_small)

         this.images.push( res.data.data[i])
          
        }
          this.store.images2 = this.images
        //console.log(this.store.images2)
         
      
    })

  },
 

}
</script>

<template>
  <div class="header">
    <h1>YU-GI-OH API</h1>
  </div>

  <div class="body">
    <AppContent></AppContent>
  </div>

  
</template>

<style>
.header{
  background-color: white;
  color: black;
  padding: 10px 30px;
}

.body{
padding: 50px;
background-color:rgba(212, 143, 56, 1) ;
}


</style>
