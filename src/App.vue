<template>
  <div id="app">
    <h1 class="title"> Calculator </h1>
    <div class="columns">
      <div class="column">
        <div class="field">
          <div class="control">
            First Number
            <input class="input" type="number" placeholder="First Number" v-model.number="first_number" @change="checkNegative" min="0" />
          </div>
        </div>
      </div>
      <div class="column">
        <div class="field">
          <div class="control">
            Second Number
            <input class="input" type="number" placeholder="Second Number" v-model.number="second_number" @change="checkNegative" min="0" />
          </div>
        </div>
      </div>      
    </div>
   
      <div class="column has-text-left">
        <p>Addition: {{ addition() }}</p>
        <p>Subtraction: {{ subtraction() }}</p>
        <p>Multiplication: {{ multiplication() }}</p>
        <p>Division: {{ division() }}</p>
      
       
      </div>  
    </div>
    
</template>

<script>

export default {
  name: 'App',
  data() {
      return {
        first_number: '0',
        second_number: '0'
      }
    },
    methods: {
      addition() {
        var firstNumber = (parseInt(this.first_number));
       var secondNumber = (parseInt(this.second_number));
       return  firstNumber+secondNumber;
       
        // return Math.round(total * 100) / 100
      },
      subtraction() {
        var firstNumber = (parseInt(this.first_number));
        var secondNumber = (parseInt(this.second_number));
        return firstNumber-secondNumber;
      },
      multiplication() {
        var firstNumber = (parseInt(this.first_number));
        var secondNumber = (parseInt(this.second_number));
        return firstNumber*secondNumber;
      },
      division() {
        var firstNumber = (parseInt(this.first_number));
        var secondNumber = (parseInt(this.second_number));
        return firstNumber/secondNumber;
      },
      
      checkNegative() {
        if (this.first_number < 0){
          this.first_number = 0;
        }
        if (this.second_number < 0){
          this.second_number = '0';
        }
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
  margin: 0px auto;
  margin-top: 60px;
  width:50%;
  padding: 2em;
  box-shadow: 0 0 5px 5px #666;
}
</style>
