<template>
  <div>
    I'm from host, but in remote Layout :)
    <button @click="handleCountAdd">Click me</button>
    <div>My counter {{ counter }}</div>
  </div>
</template>

<script>
import { reactive, toRefs } from 'vue'

export default {
 name: 'MyButton',
 setup() {
   const data = reactive({
     counter: 0,
   })

   const handleCountAdd = () => {
     data.counter++
   }

   return {
     ...toRefs(data),

     handleCountAdd
   }
 }
}
</script>

<style>

</style>