<template>
  <div id="app">
    <TodoMain />    
    <!--<Calculator />    -->        
  </div>
</template>

<script>
// import Calculator from '@/components/Calculator'
import TodoMain from '@/components/TodoMain'

export default {  
  name: 'App',    
  components: {
    TodoMain
    // Calculator,    
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

</style>
