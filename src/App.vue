<script>
import axios from 'axios'
import AppContent from './components/AppContent.vue'

export default{

  created() {
    
    
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0').then(res => {
       
         console.log(res.data.data[0].card_images)
       /* console.log(res.data.results)
        this.store.characters = res.data.results*/
    })

  },


  components:{
    AppContent
  },

    data(){
      return{

      }
    }
 

}
</script>

<template>
    <AppContent></AppContent>

  
</template>

<style>

</style>
