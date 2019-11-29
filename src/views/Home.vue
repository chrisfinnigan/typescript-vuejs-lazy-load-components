<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="This was not lazy loaded"/>
    <BeyondHelloWorld msg="This was lazy loaded" v-if="true"/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src

export default Vue.extend({
  name: 'home',
  components: {
    HelloWorld,
    // This component will be lazy loaded when it's needed
    BeyondHelloWorld: () => import(/* webpackChunkName: "BHW" */ '@/components/BeyondHelloWorld.vue'),
  },
});
</script>
