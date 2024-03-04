<script>
import {store} from '../store.js'

export default{
    name:'CardItem',

    props:{
      cardImage: String,
      cardName: String,
      cardArchetype: String,
    },

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
              
            <img :src="cardImage" alt="">
            <span>{{cardName}}</span>
            <span>{{cardArchetype}}</span>
         
</template>

<style lang="scss">

/*.layout{
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
*/
</style>