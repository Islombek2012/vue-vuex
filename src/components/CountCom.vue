<template>
      <div>
            <h1>{{count}}</h1>
            <button @click="plus">plus</button>
            <button @click="minus">minus</button>
            <button @click="reset">reset</button>
      </div>
</template>

<script setup>
import {ref, reactive} from 'vue'
      let  count = ref(0)
      function plus(){
            count.value++
            document.body.style.backgroundColor = 'green';
            if(count.value == 2){
                  document.body.style.backgroundColor = 'gray';
            }else if(count.value == 3){
                  document.body.style.backgroundColor = 'crimson';
            }else if(count.value == 4){
                  document.body.style.backgroundColor = 'pink';
            }else if(count.value == 5){
                  document.body.style.backgroundColor = 'lime';
            }
      }
      function minus(){
            count.value--
            document.body.style.backgroundColor = 'red';
             if(count.value == -3){
                  document.body.style.backgroundColor = 'gold';
            }
      }
      function reset(){
            count.value = 0
            document.body.style.backgroundColor = 'yellow';
      }
</script>

<style lang="scss" scoped>

</style>