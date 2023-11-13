<script lang="ts" setup>
const prop = defineProps({
  rating: {
    type: Number,
    required: true
  }
})
</script>

<template>
  <button type="button">
    {{ prop.rating }}
  </button>
</template>

<style scoped>
button {
  width: 3rem;
  height: 3rem;
  aspect-ratio: 1;
  background-color: var(--Dark-Blue, #262e38);
  border-radius: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  border: none;
  color: var(--Medium-Gray, #7c8798);
  text-align: center;
  font-feature-settings:
    'clig' off,
    'liga' off;

  font-family: Overpass;
  font-size: 1rem;
  font-style: normal;
  font-weight: 700;
  cursor: pointer;
}

@media (max-width: 768px) {
  button {
    width: 2rem;
    height: 2rem;
  }
}

button:hover {
  background-color: var(--Orange, #fc7614);
  color: #fff;
}

.selected {
  background-color: var(--Medium-Gray, #7c8798);
  color: #fff;
}
</style>
