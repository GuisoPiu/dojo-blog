<template>
  <div class="home">
    <h1>Home</h1> 
    <input type="text" v-model="search">
    <p>Search term - {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">{{ name }}</div> 

  </div>
</template>

<script>
// @ is an alias to /src
import { ref, computed } from 'vue'

export default {
  name: 'HomeView',
  components: {},
  setup() {
    const search = ref('')
    const names = ref(['hector', 'carlos', 'macario', 'roberot', 'irma','julio'])

    const matchingNames = computed(() => {
      return names.value.filter((name) => name.includes(search.value))
    })
    return { names, search, matchingNames }
  }
}
</script>
