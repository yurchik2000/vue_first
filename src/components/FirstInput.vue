<template>
    <div>
        <input v-bind:value="firstNumber" v-on:input="onInput" type=number placeholder="0">
    </div>
</template>

<script>
    export default {
        data() {
            return{
                firstNumber: 0
            }                        
        },        
        methods: {
            onInput(e) {
               this.firstNumber = e.target.value,
               this.$emit('response', this.firstNumber),
               console.log(this.firstNumber * this.firstNumber);
            },            
        },        
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