
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
         
         <img v-for="image in store.images2" :src="image" alt="">
</template>

<style>

</style>