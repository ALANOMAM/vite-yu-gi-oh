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

  axios.get('/*https://rickandmortyapi.com/api/character?name=rick*/')
    .then(res => {
        //console.log(res.data.results)

      //this.store.characters = res.data.results;
    });

  console.log("Ricerca percepita")
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
