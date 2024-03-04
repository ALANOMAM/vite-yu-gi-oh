
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

    <div class="card-container">

     <div class="number-of-cards">
      FOUND <span>{{ store.images2.length }}</span> CARDS
     </div>
     <div class="card-layout">
        <div v-for="image in store.images2" class="item">   
     <CardItem 
     :cardImage="image.card_images[0].image_url_small"
     :cardName="image.name"
     :cardArchetype="image.archetype"
     >
    
    </CardItem>
    </div>
    </div>
    </div>

         
</template>

<style lang="scss">

.card-container{
    background-color: white;
    padding: 20px;

    .number-of-cards{
        background-color:rgba(33, 37, 41, 1);
        padding: 5px 10px;
    }
}

.card-layout{
  display: flex;
  flex-wrap: wrap;
}

.item{   
    width: calc(100% / 5 );
     height: auto;
    /* border: 1px solid blue;*/
    padding: 10px;

    img{
        width: 100%;
    }
}

</style>