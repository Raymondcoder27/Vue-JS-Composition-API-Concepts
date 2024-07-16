<template>
  <div class="home">
    <div>
      <h3>{{ title }}</h3>
      <button class="btn" @click="decreaseCount(2)">--</button>
      <button class="btn" @click="decreaseCount(1)">-</button>
      <span class="counter">{{ counterData.count }}</span>
      <button class="btn" @click="increaseCount(1, $event)">+</button>
      <button class="btn" @click="increaseCount(2)">++</button>
    </div>
    <input type="text" v-model="title">

    <h3>{{ oddOrEven }}</h3>
  </div>
</template>

<script setup>
import {ref, reactive, computed, watch} from 'vue'

  // const count = ref(0)
  const title = ref('Counter title')

  const counterData = reactive({
    count: 0,
    title: 'My counter'
  })

  const increaseCount = (amount, e) => {
    console.log(e)
    counterData.count += amount
  }


  const decreaseCount = amount => {
    counterData.count -= amount
  }

  const oddOrEven = computed(()=> {
    if (counterData.count % 2 == 0 ) return 'even'
    return 'odd'
  })

  watch(()=> counterData.count, newValue => {
    if (newValue == 10){
      alert('You made it to 10!')
    }
  })
</script>

<style scoped>
  .home{
    text-align: center;
    padding: 20px;
  }
  .btn, .counter{
    font-size: 40px;
    padding: 10px;
    margin: 10px;
  }
</style>