<script setup>
import { reactive } from 'vue';
import Calculator from './components/Calc.vue';

const estado = reactive({
  name: 'App',
  components: {
    Calculator,
  },
})
</script>

<template>
  <div class="container">
    <Calculator />
  </div>
</template>

<style scoped>
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  margin: 0;
}

#app {
  margin-top: 60px;
}

</style>
