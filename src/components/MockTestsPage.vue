<template>
  <ion-header>
    <ion-toolbar>
    <ion-buttons slot="start">
        <ion-back-button></ion-back-button>
    </ion-buttons>
    <ion-title>Mock Tests</ion-title>
    </ion-toolbar>
  </ion-header>
  
  <ion-content class="ion-padding">
    <ion-nav-link router-direction="forward" :component="choiceLetterPageComponent">        
      <ion-item button detail lines="none" class="ion-item-border">
        <ion-label>Multiple Choice - Letter</ion-label>
        <!-- <img src="../../public/assets/imgs/word.png"/> -->
      </ion-item>
    </ion-nav-link><br>
    <ion-nav-link router-direction="forward" :component="choiceSignPageComponent">        
      <ion-item button detail lines="none" class="ion-item-border">
        <ion-label>Multiple Choice - Sign</ion-label>
        <!-- <img src="../../public/assets/imgs/word.png"/> -->
      </ion-item>
    </ion-nav-link><br>
    <ion-nav-link router-direction="forward" :component="choiceLetterPageComponent">        
      <ion-item button detail lines="none" class="ion-item-border">
        <ion-label>True or False - Letter</ion-label>
        <!-- <img src="../../public/assets/imgs/word.png"/> -->
      </ion-item>
    </ion-nav-link><br>
    <ion-nav-link router-direction="forward" :component="choiceSignPageComponent">        
      <ion-item button detail lines="none" class="ion-item-border">
        <ion-label>True or False - Sign</ion-label>
        <!-- <img src="../../public/assets/imgs/word.png"/> -->
      </ion-item>
    </ion-nav-link>
  </ion-content>
</template>
  
<script lang="ts">
  import { IonContent, IonHeader, IonTitle, IonToolbar, IonBackButton, alertController, IonNavLink } from '@ionic/vue';
  import { defineComponent } from 'vue';
  import ChoiceLetterPageComponent from './ChoiceLetterPage.vue';
  import ChoiceSignPageComponent from './ChoiceSignPage.vue';
  
  export default defineComponent({
    components: { IonContent, IonHeader, IonTitle, IonToolbar, IonBackButton, IonNavLink},
    setup() {
      const onNextBtnClick = async () => {
          const alert = await alertController.create({
          header: 'Alert',
          subHeader: 'Important message',
          message: 'This is an alert!',
          buttons: ['OK'],
          });

          await alert.present();
      };
      return { onNextBtnClick };
    },
    data() {
      return {
        choiceLetterPageComponent: ChoiceLetterPageComponent,
        choiceSignPageComponent: ChoiceSignPageComponent,
      };
    },     
  });
</script>