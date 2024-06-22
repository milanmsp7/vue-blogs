<template>
  <div class="home">
    <h2>Refs</h2>
    <p>{{ objOne.name }} - {{ objOne.age }}</p>
    <button @click="updateObjOne">Update Obj one</button>
    <h2>Reactive</h2>
    <p>{{ objTwo.name }} - {{ objTwo.age }}</p>
    <button @click="updateObjTwo">Update Obj Two</button>
  </div>
</template>

<script>
import { ref, reactive } from 'vue';
// @ is an alias to /src

export default {
  name: 'HomeView',
  setup() {
    const objOne = ref({name: 'Milan', age:26})
    const objTwo = reactive({name: 'Kattam', age:28})
    const updateObjOne = () => {
      objOne.value.name = 'MSP'
      objOne.value.age = 18
    }
    const updateObjTwo = () => {
      objTwo.name = 'Kaatoo'
      objTwo.age = 45
    }
    // return { name: name, age: age }
    return { objOne, updateObjOne,objTwo, updateObjTwo}
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
