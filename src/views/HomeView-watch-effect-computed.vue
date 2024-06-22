<template>
  <div class="home">
    <h1>Home</h1>
    <input type="text" v-model="search">
    <p>Search tern - {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">
      <p>{{ name }}</p>
    </div>
    <button @click="handleClick">Stop Watch</button>
  </div>
</template>

<script>
import { ref, computed, watch, watchEffect } from 'vue';
// @ is an alias to /src

export default {
  name: 'HomeView',
  setup() {
    // const name = computed(() => {
    //   return 'Milan'
    // })
    const search = ref('')
    const names = ref(['Milan','MSP','Kaato','Gaurang','Ram','Raju','Shakir','Deep'])

    const stopWatch = watch(search , () => {
      console.log('watch function run');
    })

    const stopEffect = watchEffect(() => {
      console.log('watchEffect function run', search.value);
    })
    const matchingNames = computed (() => {
      return names.value.filter((name)=> name.includes(search.value))
    })
    const handleClick = () => {
      stopWatch()
      stopEffect()
    }
    return { names, search, matchingNames, handleClick }
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
