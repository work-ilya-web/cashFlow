<template>
    <div class="players">        
        <div :class="['player', 'player_'+player.color]" v-for="player in players.data" v-bind:style="{left: 50 * (player.id - 1) + 5 * (player.id - 1) + 'px'}">{{player.name}}</div>
    </div>
</template>

<script>
  import axios from 'axios' 
  export default { 
    data(){
      return { 
        players: null
      }
    }, 
    mounted() {
      axios.get('https://copyl.ru/json/Players.json').then(response => (this.players = response));         
    },
    methods: {
    },
  
  }  
</script>

<style>
    .player{
        position: absolute;
        width: 50px;
        height: 50px;
        z-index: 99;
        top: 0;
        border-radius: 100px;
        color: #fff;
        display: flex;
        text-align: center;
        align-items: center;
        font-size: 12px;
        justify-content: center;
    }
    .player_blue{
        background: blue;
    }
    .player_green{
        background: green;
    }
</style>