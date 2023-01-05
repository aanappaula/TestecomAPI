<template>
  <div class="container grid-ld-my-2 py-2 text-dark">
    <h1> Hellooo</h1>
  </div>
  <div class="card">
    <div class="card-header">
      <div class="h4"> Exibindo moedas</div>
      <div class="card-body">
         <HellloWorld :quotes='quotes'/>
      </div>
    </div>
  </div>
</template>

<script>

import HellloWorld from './components/HelloWorld.vue';
import api from '@/servidor/api.js';
import { onMounted, reactive, toRefs } from 'vue';

export default {
  name: 'App',
  components: {
    HellloWorld
  },
// expor os dados da nossa API no nosso component//
setup() {
  const data = reactive ({ //dados reativos//
    quotes: {},

  });
  onMounted( async() => {
  const response = await api.all();
  data.quotes = response.data;
  })

  return  { ...toRefs(data) }
}
}
</script>

<style scoped>
.h4{
  text-align: center;
  margin-bottom: 10px;
}
.card{
  box-shadow: inset 0 0 1em gold, 0 0 1em red;
}
.card-body{
  padding: 30px;
}
</style>
