<script setup lang="ts">
defineProps<{
  //respawn function
  respawn: () => void
}>()
</script>

<template>
  <article class="card-element">
    <slot />
    <button @click="respawn">Respawn?</button>
  </article>
</template>

<style scoped>
.card-element {
  background: white;
  padding: 25px;
  max-width: 500px;
  transform: rotate(1deg);
  box-shadow: #00000022 5px 5px 2px;
  border: double #a68d67 3px;
  margin-bottom: 70px;
  padding-bottom: 30px;
}
.card-element button {
  background-color: #a68d67;
  border: 0;
  color: white;
  padding: 5px 15px;
  font-weight: bold;
  position: fixed;
  right: 0;
  bottom: 0;
  font-size: 0.9rem;
  cursor: pointer;
  transition: transform 0.2s;
}
.card-element button:hover {
  transform: scale(1.1);
}
</style>
