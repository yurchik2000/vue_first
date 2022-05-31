<template>
  <div id="app">
    <h1> Calculator </h1>            
    <span>
       <FirstInput v-on:response="" v-on:response="firstNumber = $event"  />
       <Sign v-on:response="" v-on:response="sign = $event"  />
       <SecondInput v-on:response="" v-on:response="secondNumber = $event"  />
    </span>   
    <h2> Result {{result}} </h2>    
  </div>
</template>

<script>
import FirstInput from '@/components/FirstInput'
import SecondInput from '@/components/SecondInput'
import Sign from '@/components/Sign'

export default {  
  name: 'App',  
  data() {     
    return {
      firstNumber: 0,
      secondNumber: 0,            
      sign: "+",      
    }    
  },    
  components: {
    FirstInput,
    Sign,
    SecondInput
  },  
  computed: {
    result() {
      if (this.sign === '*') return this.firstNumber * this.secondNumber
      if (this.sign === '/') return this.firstNumber / this.secondNumber
      if (this.sign === '+') return Number(this.firstNumber) + Number(this.secondNumber)
      if (this.sign === '-') return this.firstNumber - this.secondNumber      
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
span{
  display: flex;
  justify-content: space-around;
  background: gray;  
  width: 400px;
  margin: 0 auto;
  padding: 20px 5px;
  font-size: 18px;
}
</style>
