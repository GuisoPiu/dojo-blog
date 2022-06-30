<template>
  <div class="home">
    <h1>Home</h1> 
    <input type="text" v-model="search">
    <p>Search term - {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">{{ name }}</div> 
    <button @click="handleClick">stop watch</button>
  </div>
</template>

<script>
// @ is an alias to /src
import { computed, ref, watch, watchEffect } from 'vue'

export default {
  name: 'HomeView',
  components: {},
  setup() {
    const search = ref('')
    const names = ref(['hector', 'carlos', 'macario', 'roberot', 'irma','julio'])

    const stopWatch = watch(search, () => {
      console.log('input changes')
    })
    const stopEffect = watchEffect(() => {
      console.log('wathcEffect function ran', search.value)
    })

    const handleClick = () => {
      stopWatch()
      stopEffect()
    }

    const matchingNames = computed(() => {
      return names.value.filter((name) => name.includes(search.value))
    })
    return { names, search, matchingNames, handleClick }
  }
}
</script>
