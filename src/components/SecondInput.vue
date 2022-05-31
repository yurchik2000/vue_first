<template>
    <div>
        <input v-bind:value="secondNumber" v-on:input="onInput" type=number placeholder="0">
    </div>
</template>

<script>
    export default {
        data() {
            return{
                secondNumber: 0
            }                        
        },        
        methods: {
            onInput(e) {
               this.secondNumber = e.target.value,
               this.$emit('response', this.secondNumber),
               console.log(this.secondNumber * 2 );
            }
        }    
    }        
</script>

<style scoped>
    input{
        width: 80px;
        padding: 10px;
        border-radius: 10px;
        font-size: 18px;
    }
</style>