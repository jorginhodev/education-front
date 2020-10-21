<template>
  <div class="home">
    <UserInfo />

    <Events />
  </div>
</template>

<script>
import UserInfo from '@/components/UserInfo/index.vue';
import Events from '@/components/Events/index.vue';

export default {
  name: 'Home',
  components: {
    UserInfo,
    Events,
  },
};
</script>
