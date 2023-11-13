<script lang="ts" setup>
import StarItem from './icons/StarItem.vue'
import RatingItem from './RatingItem.vue'
import ButtonItem from './ButtonItem.vue'
import ThankYou from './ThankYou.vue'
import { computed, ref } from 'vue'

const selectedRating = ref<number | null>(null)

const handleRatingClick = (rating: number) => {
  selectedRating.value = rating
}

const count = ref(5)

const showRatingSection = computed(() => selectedRating.value === null)
</script>

<template>
  <section class="card">
    <div class="container" v-if="showRatingSection">
      <StarItem />

      <h1 class="title">How did we do?</h1>

      <p>
        Please let us know how we did with your support request. All feedback is appreciated to help
        us improve our offering!
      </p>

      <div class="rating-group">
        <RatingItem
          v-for="rating in count"
          :key="rating"
          :rating="rating"
          :class="{ selected: rating === selectedRating }"
          @click="handleRatingClick(rating)"
        />
      </div>

      <ButtonItem />
    </div>

    <ThankYou :selected="selectedRating ?? 0" :count="count" v-else />
  </section>
</template>

<style scope>
.card {
  width: clamp(18.75rem, 25.75rem, 100%);
  height: 26rem;
  border-radius: 1.875rem;
  background: var(
    --black-gradient,
    radial-gradient(98.96% 98.96% at 50% 0%, #232a34 0%, #181e27 100%)
  );
  padding: 2rem;
}

.container {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100%;
}

.title {
  color: var(--Pure-White, #fff);
  font-feature-settings:
    'clig' off,
    'liga' off;

  font-family: Overpass;
  font-size: 1.75rem;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
}

p {
  color: var(--Light-Grey, #969fad);
  font-feature-settings:
    'clig' off,
    'liga' off;

  font-family: Overpass;
  font-size: 0.9375rem;
  font-style: normal;
  font-weight: 400;
  line-height: 1.5rem;
}

.rating-group {
  display: flex;
  justify-content: space-between;
}
</style>
