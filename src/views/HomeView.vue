<template>
  <div class="home">
    <h1>Home</h1>
    <h2>My name is {{ name }} I'm {{ age }} years old.</h2>
    <button @click="handleClick">Click Me</button>
  </div>
</template>

<script>
export default {
  name: 'HomeView',
  setup() {
    console.log('setup');
    
    let name = 'Hussein'
    let age = 24

    const handleClick = () => {
      console.log('You clicked me.');
    }
    
    return { name, age, handleClick }
  },
}
</script>
