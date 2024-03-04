
<script>
import {store} from '../store.js'

export default{
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
            <img :src="image" alt="">
          </div>
          </div>
         
</template>

<style lang="scss">

.layout{
  display: flex;
  flex-wrap: wrap;
}

.item{
    width: calc(100% /5);
    height: auto;
    padding: 10px;

    img{
        width: 100%;
    }
}

</style>