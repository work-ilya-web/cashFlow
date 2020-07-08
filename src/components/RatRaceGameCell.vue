<template>    
  
      <div v-if="GameCell.type=='field' || GameCell.type=='empty'" :class="['field', 'field_'+GameCell.color ]" :data-id=GameCell.id>
        {{GameCell.name}}
        <span class="field__helper">{{GameCell.helper}}</span>
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
    }
  }
</script>