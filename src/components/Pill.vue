<template>
  <div class="pill" :style="{'background-color' :refreshHead(amount)}">
      <span class="name">{{ name }}</span>
      <span :style="{'color' :refreshHead(amount)}" class="amount">{{ amount }}</span>
  </div>
</template>

<script setup>
export default {
    props: ['name', 'amount'],
    methods: {
        refreshHead(value) {
            if(value < 10) {
                return 'blue'
            } else if(value < 100) {
                return 'green'
            } else if(value < 200) {
                return '#ffc400'
            } else {
                return 'red'
            }
        }
    }
}

// document.getElementsByClassName("amount").on("change", function(){
//   var coeficiente = 255/100;
//   var temperatura = document.getElementsByClassName(this).val();
//   var red  =  (temperatura * coeficiente);
//   var green =  ((temperatura * coeficiente)-255)*-1;
//   var cor = "rgb(" + red + green + ",0," + ")";
//   document.getElementsByClassName("pill").css("background-color", cor);
// })
</script>

<style scoped>
    .pill {
        margin: 10px;
        height: 55px;
        border-radius: 30px;
        color: #fff;
        font-size: 1.3rem;
        font-weight: bold;
        display: flex;
        align-items: center;
    }

    .pill .name {
        margin-left: 15px;
    }

    .pill .amount {
        margin: 10px;
        padding: 5px;
        height: 35px;
        width: 35px;
        border-radius: 18px;
        background-color: #fff;
        font-size: 14px;
        display: flex;
        justify-content: center;
        align-items: center;

    }
</style>