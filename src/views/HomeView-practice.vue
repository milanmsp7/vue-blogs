<template>
  <div class="home">
    <p>My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">Click me</button>
    <button @click="age++">Increse age</button>
    <input type="text" v-model="name">
  </div>
</template>

<script>
import { ref } from 'vue';
// @ is an alias to /src

export default {
  name: 'HomeView',
  setup() {
    console.log('setup')

    // const p = ref(null)
    // let name = 'Milan'
    // let age = 30

    const name = ref('Milan')
    const age = ref(30)

    const handleClick = () => {
      name.value = 'MSP'
      age.value = 26
    }
    // return { name: name, age: age }
    return { name, age, handleClick }
  }
  // ,
  // created() {
  //   console.log('created');
  // },
  // mounted() {
  //   console.log('mounted');
  // }
}
</script>
