<template>
  <div class="home">
    <Header />

    <UserInfo />

    <Events />
  </div>
</template>

<script>
import Header from '@/components/Header/index.vue';
import UserInfo from '@/components/UserInfo/index.vue';
import Events from '@/components/Events/index.vue';

export default {
  name: 'Home',
  components: {
    Header,
    UserInfo,
    Events,
  },
};
</script>
