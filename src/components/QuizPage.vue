<template>
  <ion-header>
    <ion-toolbar>
    <ion-buttons slot="start">
        <ion-back-button></ion-back-button>
    </ion-buttons>
    <ion-title>Quiz</ion-title>
    </ion-toolbar>
  </ion-header>
  <ion-content class="ion-padding">
  </ion-content>
</template>
  
<script lang="ts">
    import { IonHeader, IonTitle, IonToolbar, IonContent, IonButtons, IonBackButton } from '@ionic/vue';
  
    export default {
      components: { IonHeader, IonTitle, IonToolbar, IonContent, IonButtons, IonBackButton },
    };
</script>