<template>
  <category :background="'./assets/Photo.png'" :title="'Посмотреть на цветочки'" :subtitle="'27 локаций'" />
</template>

<script>
import EventCategoryCard from './components/EventCategoryCard.vue';

export default {
  name: 'App',
  components: {
    'category' : EventCategoryCard
  }
}
</script>

<style>
</style>
