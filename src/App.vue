<template>
  <Navbar @modelShow="modelToggle()"></Navbar>
  <Expences :allExpences="expence"></Expences>
  <Model 
    @model-toggle="modelToggle()" 
    @store-expence="storeExpence" 
    :status="modelStatus" 
  />
</template>

<script>
import Navbar from './components/Navbar'
import Model from './components/Model'
import Expences from './components/Expence'
export default {
  name: 'App',
  components: {
    Navbar,
    Model,
    Expences
  },
  data(){
    return{
      modelStatus: false,
      expence:{
        balance:0,
        income:0,
        expence:0,
        history: [],
      }
    }
  },
  methods:{
    modelToggle(){
      this.modelStatus = !this.modelStatus;
    },
    storeExpence(payload){
      const number = Number.parseInt(payload.number);
      if(number >= 1){
        this.expence.income += number;
        this.expence.balance += number;
      }else{
        this.expence.expence += number
        this.expence.balance += number
      }
      this.expence.history = [{title: payload.title, number: payload.number}, ...this.expence.history];
      // console.log(this.expence.balance, this.expence.income, this.expence.expence);
      this.modelStatus = false;
      
      
      
      
    }
  }
}
</script>

<style>
*{
  margin : 0;
  padding : 0;
  box-sizing: border-box;
}
body{
  background : #fafafa;
  font-family: sans-serif;

}
</style>
