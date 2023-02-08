<template>
  <div class="container">
    <h1 class="header">Color Picker Game</h1>

    <div class="message">{{ message }}</div>

    <button
      v-for="color in colors"
      class="btn"
      :key="color"
      @click="matchColor(color)"
    >
      {{ color }}
    </button>
  </div>
</template>

<script>
import { colorManager } from '../composables/color-game-manager';

export default {
  setup() {
    const { colors, message, matchColor } = colorManager();

    return { colors, message, matchColor };
  }
};
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  min-height: 100vh;
  text-align: center;
}

.header {
  font-weight: 600;
  text-transform: uppercase;
}

.message {
  padding: 20px 0;
  font-size: 1.5rem;
}

.btn {
  margin: 5px 0;
  padding: 10px;
  border-radius: 5px;
  cursor: pointer;
  text-transform: capitalize;
  font-size: 1.2rem;
}

.btn:hover {
  background-color: brown;
  color: #fff;
}
</style>
