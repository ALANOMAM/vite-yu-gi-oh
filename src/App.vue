<script>
import AppOptions from './components/AppOptions.vue'
import axios from 'axios'
import {store} from './store.js'
import AppContent from './components/AppContent.vue'

export default{



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
          //console.log(res.data.data[i])
         // this.images.push( res.data.data[i].card_images[0].image_url_small)

         this.images.push( res.data.data[i])
          
        }
          this.store.images2 = this.images
        //console.log(this.store.images2)
         
      
    })

  },


  components:{
    AppContent,
    AppOptions
  },

  methods: {

searchCard() {

    // console.log('Richiesta di filtro')
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0&archetype=' + this.store.filterValue) 
        .then(res => {
          // console.log('carte', res.data.data)
           this.store.images2 = res.data.data;
      });
     
    //console.log("Ricerca percepita")
},

},
 

}
</script>

<template>
  <div class="header">
    <h1>YU-GI-OH API</h1>
  </div>

  
  <div class="body">
    <AppOptions @search="searchCard()"></AppOptions>
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
