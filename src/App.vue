<template>
  <!-- <h1>Padre</h1> -->
  <div>
    <div v-for="(cosa,index) in cosas" :key="index">
      <FichaVue :cosa="cosa" :index="index" @retorno="retorno"/>

    </div>
  </div>


</template>


<script setup>
import FichaVue from './components/Ficha.vue';
import cosas from "./assets/datos"

const retorno=(a,i)=>{
  if(a>=6){
    cosas.value[i].nota=1;
    
  }else {
    cosas.value[i].nota=a+1;
  }
}
</script>


<style scoped>

</style>
