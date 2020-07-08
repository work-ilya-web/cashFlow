<template>
    <div class="rolls">
        <select name="countRolls" id="countRolls">
            <option value="1" selected>1</option>
            <option value="2">2</option>
            <option value="3">3</option>
        </select>
        <button type="button" class="dice-roll">Кинуть кубики</button>
    </div>
</template>

<script>
    
    export default {   
        props: [],
    }
</script>
