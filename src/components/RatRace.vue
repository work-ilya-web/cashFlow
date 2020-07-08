<template>
   
    <div id="rat-race"  class="flex rat-race">       
        <rat-race-game-cell  v-for="GameCell in items" v-bind:GameCell="GameCell"></rat-race-game-cell>
        <players></players>
    </div>
</template>

<script>
    import RatRaceGameCell from './RatRaceGameCell.vue';
    import Players from './Players.vue';
    export default {   
        props: ['items'],
        components: {
            RatRaceGameCell: RatRaceGameCell,
            Players: Players,
        }
        
    }
    
    
</script>
