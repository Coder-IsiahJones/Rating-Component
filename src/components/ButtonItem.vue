<script lang="ts" setup>
const prop = defineProps({
  title: {
    type: String,
    required: true,
    default: 'Submit'
  }
})
</script>

<template>
  <button type="button">{{ prop.title }}</button>
</template>

<style scoped>
button {
  border-radius: 1.4063rem;
  background: var(--Orange, #fc7614);
  width: 100%;
  height: 2.8125rem;
  color: var(--Pure-White, #fff);
  font-feature-settings:
    'clig' off,
    'liga' off;

  font-family: Overpass;
  font-size: 0.9375rem;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
  letter-spacing: 0.125rem;
  border: none;
  cursor: pointer;
}

button:hover {
  color: var(--Orange, #fc7614);
  background: #fff;
}

button:focus {
  color: var(--Orange, #fc7614);
  background: #fff;
  outline: 2px solid var(--Orange, #fc7614);
  outline-offset: 2px;
}
</style>
