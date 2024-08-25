<template>
  <div>
    Home Vue
    <ul>
      <li>{{data}}</li>
    </ul>
    <div class="card">
        <div class="mini-card"  v-for="data in datas" :key="data.id">
          <img :src="data.image" :alt="data.id">
          <h1>{{data.title}}</h1>
          <p>{{data.count}}</p>
        </div>
    </div>
  </div>
</template>

<script setup>
  import {ref, reactive, onMounted} from 'vue'
  const datas = ref([])
  onMounted( async()=>{
    try{
      const req = await fetch('https://fakestoreapi.com/products')
    if(req.status !== 200){
      throw new Error('Error')
    }
    const res = await req.json()
    datas.value = res
    }catch(e){
      alert(e)
    }
  })
</script>

<style scoped>
  .card{
    display: grid;
    grid-template-columns: repeat(3,300px);
    align-items: center;
    gap: 100px;
  }
  .mini-card{
    width: 400px;

  }
  .mini-card img{
    width: 300px;
    height: 300px;
  }
</style>