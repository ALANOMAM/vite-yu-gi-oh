
<script>
import CardItem from './CardItem.vue'
import {store} from '../store.js'

export default{

    components:{
     CardItem
    },

    name:'AppContent',


  data(){
       return{
        store,
       }
  },

  methods:{
    
  }


}
</script>

<template>  
     <div class="layout">
        <div v-for="image in store.images2" class="item">   
     <CardItem 
     :cardImage="image.card_images[0].image_url_small"
     :cardName="image.name"
     :cardArchetype="image.archetype"
     >
    
    </CardItem>
    </div>
    </div>
            
          <!--<div class="layout">
          <div v-for="image in store.images2" class="item">
            <img :src="image.card_images[0].image_url_small" alt="">
            <span>{{image.name}}</span>
            <span>{{image.archetype}}</span>
          </div>
          </div> -->
         
</template>

<style lang="scss">

.layout{
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

.item{
    width: calc(100% /5);
    height: auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap:20px;
    background-color:rgba(212, 143, 56, 1) ;

    img{
        width: 100%;
    }
}

</style>