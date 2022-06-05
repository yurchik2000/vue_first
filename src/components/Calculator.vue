<template> 
    <div>
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
  name: 'Calculator',  
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
