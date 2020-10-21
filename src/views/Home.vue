<template>
  <div class="home">
    <h1>Milão</h1>

    <events />
  </div>
</template>

<script>
import Events from '../components/Events/index.vue';

export default {
  name: 'Home',
  components: {
    Events,
  },
};
</script>
