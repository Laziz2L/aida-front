<template>
  <!-- <category :background="'./assets/Photo.png'" :title="'Посмотреть на цветочки'" :subtitle="'27 локаций'" /> -->
  <registration />
</template>

<script>
// import EventCategoryCard from './components/EventCategoryCard.vue';
import Registration from './components/Registration.vue';

export default {
  name: 'App',
  components: {
    // 'category' : EventCategoryCard,
    Registration
  }
}
</script>

<style>
</style>
