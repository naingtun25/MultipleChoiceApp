<template>
  <ion-header>
    <ion-toolbar>
    <ion-buttons slot="start">
        <ion-back-button></ion-back-button>
    </ion-buttons>
    <ion-title>Multiple Choice</ion-title>
    </ion-toolbar>
  </ion-header>
  
  <ion-content style="text-align: center;" class="ion-padding">
    <div class="container">
      <div class="content-center">
        <ion-nav-link router-direction="forward" :component="choiceLetterPageComponent">        
          <ion-button color="gradient3" shape="round" class="card-btn">Choice Letter</ion-button><br><br>
        </ion-nav-link>
        <ion-nav-link router-direction="forward" :component="choicePicturePageComponent">        
          <ion-button color="gradient3"  shape="round" class="card-btn">Choice Picture</ion-button><br><br>
        </ion-nav-link>
      </div>
    </div>
  </ion-content>
</template>
  
<script lang="ts">
  import { IonContent, IonHeader, IonTitle, IonToolbar, IonButton, IonBackButton, alertController, IonNavLink } from '@ionic/vue';
  import { defineComponent } from 'vue';
  import ChoiceLetterPageComponent from './ChoiceLetterPage.vue';
  import ChoicePicturePageComponent from './ChoicePicturePage.vue';
  
  export default defineComponent({
    components: { IonContent, IonHeader, IonTitle, IonToolbar, IonButton, IonBackButton, IonNavLink},
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
        choicePicturePageComponent: ChoicePicturePageComponent,
      };
    },     
  });
</script>