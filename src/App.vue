<template> 
      <div>
        
        <rat-race  v-bind:items="fields.data"></rat-race>  
      </div> 
</template>
 
<script>
  import RatRace from './components/RatRace.vue'
  import axios from 'axios' 
  export default { 
    data(){
      return { 
        fields: null
      }
    }, 
    components: {
      RatRace : RatRace
    },
    mounted() {
      axios.get('https://copyl.ru/json/RatRase.json').then(response => (this.fields = response));         
    }
  }
  
</script>

