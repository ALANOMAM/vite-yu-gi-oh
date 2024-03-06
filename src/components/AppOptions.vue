
<script>
import {store} from '../store.js'
import axios from 'axios'
   export default{
       name:"AppOptions",

       data(){
          return{
             //array che riempirò con i vari elementi
             selectItems:[],
             store
          }
       }, 

     created() {
    
    
    axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php').then(res => {
       
        
        for(let i=0; i<res.data.length; i++){
      //riempio il mio array con i vari elementi che poi userò per il select   
          this.selectItems.push(res.data[i].archetype_name)
        }

         //console.log( this.selectItems)
    })

  },



   }

   

</script>

<template>
    <!--@change fa in modo tale che ogni volta che cambio il valore delle options viene emmesso l'evento @search-->
     <select
      @change="$emit('search')" 
      v-model="store.filterValue" 
      name="options" id="card-options">

        <option value="">Scegliere una opzione di archetype name</option>
        <option  v-for="archetype in selectItems"  :value="archetype">{{ archetype }}</option>  

   </select>

</template>

<style lang="scss">

#card-options{
padding: 5px 10px;
margin-bottom: 20px;
border: 2px solid white;
border-radius: 5px;
}

</style>