<script setup>
  import { ref} from 'vue'
  import Presupuesto from './components/Presupuesto.vue'
  
  const presupuesto =ref(0);

  const definirPresupuesto = cantidad =>{
    presupuesto.value= cantidad
    console.log(cantidad);
  }

</script>

<template>
  <div>
    <header>
    <h1>planificador de Gastos</h1>
    <div
      class="contenedor-header contenedor sombra"
    >
      <Presupuesto
      v-if="presupuesto === 0"
        @definir-presupuesto="definirPresupuesto"
      />
      <p v-else>
        {{ presupuesto }}
      </p>
    </div>
    
  </header>



  </div>
  
</template>

<style>
  :root{
    --azul: #3b82f6;
    --blanco: #FFF;
    --gris-claro: #e0e0e0;
    --gris: #bdbdbd;
    --gris-oscuro: #64748b;
    --negro:#000;
  }

  html{
    font-size: 62.5%;
    box-sizing: border-box;
  }

*,
*:before,
*::after{
  box-sizing: inherit;
}

body{
  font-size: 1.6rem;
  font-family: 'Lato', sans-serif;
  background-color: var(--gris-claro);
}

h1{
  font-size:4rem;
}

h2{
  font-size:3rem;
}

header{
  background-color: var(--azul);
}

header h1{
  padding: 3rem 0;
  margin: 0;
  color: var(--blanco);
  text-align: center;
}

.contenedor{
  width: 90%;
  max-width: 80rem;
  margin: auto;
}

.contenedor-header{
  margin-top: -5rem;
  transform: translateY(5rem);
  padding: 5rem;
}

.sombra{
  box-shadow: 0px 10px 15px -3px rgba(0,0,0,0.1);
  background-color: var(--blanco);
  border-radius: 1.2rem;
  padding: 5rem;
}



</style>
