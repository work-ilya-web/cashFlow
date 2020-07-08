<template> 
      <div >        
        <rat-race  v-bind:items="fields.data"></rat-race>  
      </div> 
</template>
 
<script>
  import RatRace from './components/RatRace.vue'
  import axios from 'axios' 
  export default { 
    data(){
      return { 
        fields: null,
        element: document.querySelector('[data-event="start"')
      }
    }, 
    components: {
      RatRace : RatRace
    },
    mounted() {
      axios.get('https://copyl.ru/json/RatRase.json').then(response => (this.fields = response));         
    },
    methods: {
      someMethod: function (event) {
        console.log(this.element.getBoundingClientRect());
         
        this.$refs.start.innerText = "Welcome to Vue.js";
      }
    },
  
  }
  
</script>

