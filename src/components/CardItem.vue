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
              <div class="item-content">
            <img :src="cardImage" alt="">
            <span>{{cardName}}</span>
            <span>{{cardArchetype}}</span>
             </div>
</template>

<style lang="scss">

.item-content{
    /*border: 1px red solid;*/
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap:20px;
    background-color:rgba(212, 143, 56, 1) ;
}

</style>