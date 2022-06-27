<template>
  <div class="home">
    <h1>Home</h1> 
    <h2>Refs</h2>
    <p>{{ ninjaOne.name }} - {{ ninjaOne.age }}</p>
    <button @click="updateNinjaOne">click me</button>
    <h2>Reactive</h2>
    <p>{{ ninjaTwo.name }} - {{ ninjaTwo.age }}</p>
    <button @click="updateNinjaTwo">click me</button>
  </div>
</template>

<script>
// @ is an alias to /src
import { ref, reactive } from 'vue'

export default {
  name: 'HomeView',
  components: {},
  setup() {
    // const p = ref(null)
    
    const ninjaOne = ref({name: 'mario', age: 30 })
    const ninjaTwo = reactive({name: 'luigi', age: 40 })

    const updateNinjaOne = () => { 
      ninjaOne.value.age = 35
    }

    const updateNinjaTwo = () => { 
      ninjaTwo.name = 'Rios',
      ninjaTwo.age = 55
     }

    return { name, ninjaOne, ninjaTwo, updateNinjaOne, updateNinjaTwo }
  }
}
</script>
