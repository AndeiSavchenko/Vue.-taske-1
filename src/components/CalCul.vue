<template>
  <div>
       <input v-model.number="operand1" />
       <input v-model.number="operand2" />
       <br>
       =  {{ result }}
       <br>
      <button @click="sum">+</button>
      <button @click="difference">-</button>
      <button @click="sub">/</button>
      <button @click="multiply">*</button>
      <button @click="expon">^</button>
      <button @click="subWithout">цел.число</button>
  </div>
</template>

<script>
export default {
   name:"CalCul",
   data(){
     return {
     result: 0,
     operand1: 0,
     operand2: 0
     }
    },
    methods: {
      sum() {
        this.result = this.operand1 + this.operand2
      },
      difference() {
        this.result = this.operand1 - this.operand2
      },
      sub() {
        if (this.operand2 == 0) {
          this.result = "на ноль делить нельзя"
        } else {
          this.result = this.operand1 / this.operand2 
        }
      },
      multiply() {
        this.result = this.operand1 * this.operand2
      },
      expon() {
        this.result = Math.pow(this.operand1, this.operand2)
      },
      subWithout() {
            if (this.operand2 == 0) {
          this.result = "на ноль делить нельзя"
        } else {
          this.result = parseInt(this.operand1/this.operand2) 
        }
      }
    }
}
</script>

<style>

</style>