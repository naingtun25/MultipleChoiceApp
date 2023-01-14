<template>
  <ion-nav :root="component"></ion-nav>
</template>

<script lang="ts">
  import { IonNav } from '@ionic/vue';
  import { defineComponent } from 'vue';

  import HomePage from './components/HomePage.vue'

  export default defineComponent({
    name: 'App',
    components: { IonNav },
    data() {
        return {
          component: HomePage,
        };
      },
  });
</script>
