<template>
  <div class="home">
    <h1>Home</h1>
    <p ref="p">My name is {{ name }} I'm {{ age }} years old.</p>
    <button @click="handleClick">Click Me</button>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'HomeView',
  setup() {
    const p = ref(null)
    
    let name = 'Hussein'
    let age = 24

    const handleClick = () => {
      console.log(p, p.value)
      p.value.classList.add('test')
      p.value.textContent = 'Hello again.'
    }
    
    return { name, age, handleClick, p }
  },
}
</script>
