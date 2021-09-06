<template>
  <div class="event-category-card">
    <img :src="background" class="event-category-card__background">
    <div class="event-category-card__info">
      <h3 class="event-category-card__title">{{ title }}</h3>
      <h3 class="event-category-card__subtitle">{{ subtitle }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  props: [
    'background',
    'title',
    'subtitle',
  ]
}
</script>

<style>

</style>