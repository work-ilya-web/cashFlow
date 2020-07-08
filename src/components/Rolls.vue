<template>
    <div class="rolls">
        <div class="flex">
            <select name="countRolls" v-model="countRolls" id="countRolls">
                <option value="1" selected>1</option>
                <option value="2">2</option>
                <option value="3">3</option>
            </select>
            <button type="button" class="dice-roll" v-on:click="greet">Кинуть кубики</button>
        </div>
        
        <div class="result">{{result}}</div>        
    </div>
</template>

<script>
    
    export default {   
        data(){
            return { 
                countRolls: 1,
                side: [],
                diceTotal: 0,
                result: '',
                i: 0
            }
        },
        methods: {
            greet: function (event) {
                this.result = '';
                this.diceTotal = 0;
                for ( this.i = 1; this.i <= this.countRolls; this.i++) {
                    this.side[this.i] = Math.floor(Math.random() * 6) + 1;
                    this.diceTotal = parseInt(this.diceTotal) + parseInt(this.side[this.i]);                      
                    if(this.countRolls>1){
                        if (this.i == this.countRolls) {
                            this.result =  this.result + this.side[this.i] + ' = ' + this.diceTotal;
                        } else {
                            this.result =  this.result + this.side[this.i] + ' + ';
                        }        
                    } else {
                        this.result = this.result + this.side[this.i];
                    }
                }               
            }
        }
    }
</script>

<style scoped>
    #countRolls{    
        height: 40px;
        width: 60px;
        margin-right: 3px;  
    }
    button{
        width: 100%;
        cursor: pointer;
    }
    .result{
        margin-top: 5px;
        text-align: center;
    }
</style>
