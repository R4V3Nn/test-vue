<template>
  <div class="total-currency">
     Total Currency : {{ totalCurrency }} 
  </div>
</template>

<script>
export default {
  props : ['data'],
  computed : {
      totalCurrency() {
         return this.data.reduce(function(sum, current){
             return sum + current.currency;
         },0) 
      }
  }
}
</script>

<style>

    .total-currency {
        font-size: 20px;
        width: 220px;
        margin-left: 70%;
        margin-bottom: 20px;
    }
</style>


