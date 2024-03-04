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
    
    
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0').then(res => {
       

        for(let i=0; i<res.data.data.length; i++ ){
         // console.log(res.data.data[i].card_images)
          this.images.push( res.data.data[i].card_images[0].image_url_small)
          
        }
          this.store.images2 = this.images
        console.log(this.store.images2)
         
       /* console.log(res.data.results)
        this.store.characters = res.data.results*/
    })

  },
 

}
</script>

<template>
    <AppContent></AppContent>

  
</template>

<style>

</style>
