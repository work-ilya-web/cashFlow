<template>    
    <div v-if="item.type=='field' || item.type=='empty'" :class="['field', 'field_'+item.color ]" :data-id=item.id>{{item.name}} <span class="field__helper">{{item.helper}}</span></div>    
    <div v-else-if="item.type=='rolls'" class="field">
        <rolls></rolls>  
    </div>    
    <div v-else class="field">{{item.type}}</div>    
</template>

<script>
  import Rolls from './Rolls.vue'
  export default {  
    props: ['item'],
    components: {
      Rolls : Rolls
    }
  }
</script>