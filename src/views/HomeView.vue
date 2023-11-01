<template>
  <div class="home">
    <h1>Home</h1>
    <p>My name is {{ name }} I'm {{ age }} years old.</p>
    <button @click="handleClick">Click Me</button>
    <button @click="age++">Add 1 to age</button>
    <input type="text" v-model="name">
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'HomeView',
  setup() {
    
    const name = ref('Hussein')
    const age = ref(24)

    const handleClick = () => {
      name.value = 'Joe'
      age.value = 20
    }
    
    return { name, age, handleClick }
  },
}
</script>
