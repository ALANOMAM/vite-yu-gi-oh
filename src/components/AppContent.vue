
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
         <img :src="store.images2[0]" alt="">
</template>

<style>

</style>