<template>
  

    <div class="calc">
      <div class="display">
        <display-calculator @click="clearDisplay" :value='String(acumulator)'  :result="result" />
      </div>

      <div class="keys-group">
        <button-calculator v-for="key in keys" :value='key' @click='handleClick(key)'/>
      </div>
    
    </div>


</template>

<script setup>
import { ref } from 'vue'
import ButtonCalculator from './ButtonCalculator.vue'
import DisplayCalculator from './DisplayCalculator.vue'

let acumulator = ref('Calculator')

let result = ref('')

const keys = [
  '7' , '8' , '9', '/',
  '4' , '5' , '6', '-',
  '1' , '2' , '3', '+',
  '0' , '.' , '=', '*',
  ] 



function clearDisplay(){
  acumulator.value = 'Calculator'
  result.value = ''
}



const resultCalculated = ()=>{
result.value = eval(acumulator.value)

}


const handleClick = (n)=>{

const lastKeyClicked = String(acumulator.value)[acumulator.value.length- 1]
  
  if(lastKeyClicked == '-' ||lastKeyClicked == '*'|| lastKeyClicked == '/'|| lastKeyClicked == '+'|| lastKeyClicked == '.'   ){
    if(n=='-'||n=='*'||n=='/'||n=='+'||n=='.'){
      return
    }
  }

  if(acumulator.value == 'Calculator' )acumulator.value = '';
  if(n == '=')resultCalculated();
  
  else{
  acumulator.value += n
  }
  
}




</script>

<style>
.keys-group {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  align-items: center;
  grid-gap: 2px;
  height: 70vh;
}

.display{
  background-color: rgb(107, 107, 52);
  margin-bottom: 10px;
  border-radius: 3px;
  height: 20vh;
}

.calc{
  
  padding: 10px;
  border-radius: 4px;
  box-shadow: 1px 1px 2px 1px rgb(129, 129, 129);
  max-width: 100%;
  height: 100vh;
  margin-left: auto;
  margin-right: auto;
  background-color: beige;
}



</style>