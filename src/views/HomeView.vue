<template>
  <div class="home">
    <h1>Home</h1>
    <h2>Refs</h2>
    <p>{{ nameOne.name }} - {{ nameOne.age }}</p>
    <button @click="updateNameOne">Update name one</button>
    <h2>Reactive</h2>
    <p>{{ nameTwo.name }} - {{ nameTwo.age }}</p>
    <button @click="updateNameTwo">Update name two</button>
  </div>
</template>

<script>
import { reactive, ref } from 'vue'

export default {
  name: 'HomeView',
  setup() {
    
    const nameOne = ref({name: 'Hussein', age: 24})
    const nameTwo = reactive({name: 'Mark', age: 31})

    const updateNameOne = () => {
      nameOne.value.name = 'Joe'
      nameOne.value.age = 20
    }
    
    const updateNameTwo = () => {
      nameTwo.name = 'Josh'
      nameTwo.age = 28
    }

    return { nameOne, updateNameOne, nameTwo, updateNameTwo }
  },
}
</script>
