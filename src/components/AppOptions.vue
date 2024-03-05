
<script>
import axios from 'axios'
   export default{
       name:"AppOptions",

       data(){
          return{
             //array che riempirò con i vari elementi
             selectItems:[]
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
    
    <select name="options" id="card-options">
        <option value="">Scegliere una opzione</option>
        <option value="">yo</option>
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