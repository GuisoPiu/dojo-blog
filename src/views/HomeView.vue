<template>
  <div class="home">
    <p ref="p">My name is {{ name }} and my age is {{ age }}</p>  
    <button @click="handleClick">click me</button>
    <button @click="age++">add 1 to age</button>
    <input type="text" v-model="name">
  </div>
</template>

<script>
// @ is an alias to /src
import { ref } from 'vue'

export default {
  name: 'HomeView',
  components: {},
  setup() {
    // const p = ref(null)
    
    const name = ref('mario')
    const age = ref(30)

    const handleClick = () => {
      name.value = 'luigi'
      age.value = 35
    }

    return { name, age, handleClick }
  }
}
</script>
