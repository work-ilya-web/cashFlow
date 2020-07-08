<template>    
  
      <div v-if="GameCell.type=='field' || GameCell.type=='empty'" :ref=GameCell.event :class="['field', 'field_'+GameCell.color ]" :data-id=GameCell.id>
        {{GameCell.name}}
        <span class="field__helper">{{GameCell.helper}}</span>
        <span class="field__start" v-if="GameCell.event=='start'">{{GameCell.event}}</span>
      </div>    
      <div v-else-if="GameCell.type=='rolls'" class="field">
          <rolls></rolls>  
      </div>    
      <div v-else class="field">{{GameCell.type}}</div>   
    
</template>

<script>
  import Rolls from './Rolls.vue'
  export default {  
    props: ['GameCell'],
    components: {
      Rolls : Rolls
    },
    mounted() {       
       this.coordinatesStart;
       window.addEventListener('resize', this.coordinatesStart)
    },
    updated() {       
       this.coordinatesStart;
    },
    methods: {
      coordinatesStart: function (event) {
        if(this.GameCell.event == 'start'){
            console.log( this.$refs.start.getBoundingClientRect());           
        }
      }
    }
  }
  
</script>