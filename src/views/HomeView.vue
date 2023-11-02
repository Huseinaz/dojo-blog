<template>
  <div class="home">
    <h1>Home</h1>
    <input type="text" v-model="search">
    <!-- <p>Search term - {{ search }}</p> -->
    <div v-for="name in matchingNames" :key="name">{{ name }}</div>
    <button @click="handleClick">Stop Watching</button>
  </div>
</template>

<script>
import { computed, ref, watch, watchEffect } from 'vue'

export default {
  name: 'HomeView',
  setup() {
    const search = ref('')
    const names = ref(['mario', 'yoshi', 'luigi', 'toad', 'bowser', 'koopa', 'peach'])

    const matchingNames = computed(() => {
      return names.value.filter((name) => name.includes(search.value))
    })

    const stopWatch = watch(search, () => {   //watch search when it changes
      console.log('watch function ran');
    })

    const stopEffect = watchEffect(() => {
      console.log('watchEffect function ran', search.value);
    })

    const handleClick = () => {
      stopWatch()
      stopEffect()
    }

    return { names, search, matchingNames, handleClick }
  },
}
</script>
