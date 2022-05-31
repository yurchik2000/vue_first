<template>
    <div>
        <input v-bind:value="sign" v-on:input="onInput" type=text placeholder="+, -, *, /">
    </div>
</template>

<script>
    export default {
        data() {
            return{
                sign: ""
            }                        
        },        
        methods: {
            onInput(e) {
               this.sign = e.target.value,
               this.$emit('response', this.sign)
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