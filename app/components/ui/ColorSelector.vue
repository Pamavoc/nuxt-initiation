<template>
    <div class="color-selector">
      <h2>{{ title }}</h2>
      <p>{{ description }}</p>
      <button v-if="type === 'select'" @click="emitRandomColor">Générer une couleur</button>
      <select v-else-if="type === 'dropdown'" @change="emitRandomColor">
        <option>Couleur 1</option>
        <option>Couleur 2</option>
        <option>Couleur 3</option>
      </select>
    </div>
  </template>
  
  <script setup>
  import { defineProps, defineEmits } from "vue";
  
  // Définir la prop attendue
  defineProps({
    type: {
      type: String,
      default: "select", // 'select' ou 'dropdown'
    },
  });
  
  // Définir les événements que l'enfant peut émettre
  const emit = defineEmits(["color-selected"]);
  
  // Génère une couleur aléatoire au format hexadécimal
  const generateRandomColor = () => {
    const letters = "0123456789ABCDEF";
    let color = "#";
    for (let i = 0; i < 6; i++) {
      color += letters[Math.floor(Math.random() * 16)];
    }
    return color;
  };
  
  // Émet la couleur générée au parent
  const emitRandomColor = () => {
    const color = generateRandomColor();
    emit("color-selected", color);
  };
  </script>
  
  <style>
  .color-selector {
    text-align: center;
  }
  
  button {
    padding: 10px 20px;
    background-color: #4caf50;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #45a049;
  }
  </style>
  