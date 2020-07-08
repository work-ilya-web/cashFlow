<template>
    <div id="rat-race"  class="flex rat-race">
        <rat-race-game-cell  v-for="item in items" v-bind:item="item"></rat-race-game-cell>
    </div>
</template>

<script>
    import RatRaceGameCell from './RatRaceGameCell.vue';
    export default {   
        props: ['items'],
        components: {
            RatRaceGameCell: RatRaceGameCell
        }
    }
</script>
