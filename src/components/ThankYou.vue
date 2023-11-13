<script lang="ts" setup>
import PhoneItem from './icons/PhoneItem.vue'

const prop = defineProps({
  selected: {
    type: Number,
    required: true
  },
  count: {
    type: Number,
    required: true
  }
})
</script>
<template>
  <div class="container">
    <PhoneItem />

    <div class="pill">
      <span class="outcome">You selected {{ prop.selected }} out of {{ prop.count }}</span>
    </div>

    <div class="thankyou">
      <h1 class="title">Thank you!</h1>

      <span class="text"
        >We appreciate you taking the time to give a rating. If you ever need more support, don’t
        hesitate to get in touch!</span
      >
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  height: 100%;
}

.title {
  color: #fff;
  font-feature-settings:
    'clig' off,
    'liga' off;

  font-family: Overpass;
  font-size: 1.75rem;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
}

.text {
  color: var(--Light-Grey, #969fad);
  text-align: center;
  font-feature-settings:
    'clig' off,
    'liga' off;

  font-family: Overpass;
  font-size: 0.9375rem;
  font-style: normal;
  font-weight: 400;
  line-height: 1.5rem;
}

.pill {
  border-radius: 1.4063rem;
  background: var(--Dark-Blue, #262e38);
  padding: 0.25rem 1.25rem;
}

.outcome {
  color: var(--Orange, #fc7614);
  text-align: center;
  font-family: Overpass;
  font-size: 0.9375rem;
  font-style: normal;
  font-weight: 400;
}

.thankyou {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
}
</style>
