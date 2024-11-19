<template>
    <div class="background-display" :style="{ backgroundColor: backgroundColor }">
        <h1>Parennt Background Selector</h1>
        <UiColorSelector 
        type="select"
        @color-selected="handleColorSelected">
        </UiColorSelector>
    </div>
</template>

<script setup lang="ts">
const backgroundColor = ref("white");

const handleColorSelected = (color: string) => {
    console.log("Couleur sélectionnée :", color);
    backgroundColor.value = color;
};

</script>

<style scoped lang="scss">
.background-display {
    transition: background-color 0.3s;
    padding: 20px;
    color: black;
    display: flex;
    flex-direction: column;
    align-items: center;
}
</style>

  