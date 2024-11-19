<template>
    <div>
      <h1>Compteur : {{ count }}</h1>
      <button @click="increment">Incrémenter</button>
      <button @click="reset">Réinitialiser</button>
    </div>
  </template>
  
  <script setup>
  // rend la valeur réactive
  import { ref } from "vue";
  
  // on crée une constante car elle est "immutable", c'est la valeur dedans qui va changer
  const count = ref(0);
  // la valeur est accessible par .value car on accède à la valeur réactive du ref

  const increment = () => {
    count.value++;
  };
  
  const reset = () => {
    count.value = 0;
  };
  </script>
  