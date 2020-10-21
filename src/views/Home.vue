<template>
  <div class="home">
    <Header />

    <Events />
  </div>
</template>

<script>
import Header from '@/components/Header/index.vue';
import Events from '@/components/Events/index.vue';

export default {
  name: 'Home',
  components: {
    Header,
    Events,
  },
};
</script>
