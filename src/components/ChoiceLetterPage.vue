<template>
  <ion-header>
    <ion-toolbar>
    <ion-buttons slot="start">
        <ion-back-button></ion-back-button>
    </ion-buttons>
    <ion-title>Choice Letter</ion-title>
    </ion-toolbar>
  </ion-header>

  <ion-content color="gradient2" class="ion-padding ion-text-center">
    <ion-item color="transparent" lines="none">
      <img src="../../public/assets/imgs/car1.png" class="center round-border-img"/>
    </ion-item><br>
    <ion-radio-group value="0">
      <ion-item color="transparent" lines="none">
        <img src="../../public/assets/imgs/gradient-border.png"/>
        <ion-radio slot="start" value="1"></ion-radio>
      </ion-item>
      <ion-item color="transparent" lines="none">
        <img src="../../public/assets/imgs/gradient-border.png"/>
        <ion-radio slot="start" value="2"></ion-radio>
      </ion-item>
      <ion-item color="transparent" lines="none">
        <img src="../../public/assets/imgs/gradient-border.png"/>
        <ion-radio slot="start" value="3"></ion-radio>
      </ion-item>
      <ion-item color="transparent" lines="none">
        <img src="../../public/assets/imgs/gradient-border.png"/>
        <ion-radio class="radio-md" slot="start" value="4"></ion-radio>
      </ion-item>
    </ion-radio-group>
  </ion-content>
</template>
  
<script>
    import { defineComponent } from 'vue';
    import { IonHeader, IonTitle, IonToolbar, IonContent, IonButtons, IonBackButton, IonRadioGroup, IonRadio, IonItem} from '@ionic/vue';
  
    export default defineComponent({
      components: { IonHeader, IonTitle, IonToolbar, IonContent, IonButtons, IonBackButton, IonRadioGroup, IonRadio, IonItem },
    })
</script>