<template>
  <ion-header>
    <ion-toolbar>
      <ion-title>Home</ion-title>
    </ion-toolbar>
  </ion-header>
  
  <ion-content style="text-align: center;" class="ion-padding">
    <ion-nav-link router-direction="forward" :component="studyPageComponent">        
      <ion-button color="gradient3" class="card-btn">Study</ion-button><br><br>
    </ion-nav-link>
    <ion-nav-link router-direction="forward" :component="quizPageComponent">        
      <ion-button color="gradient3" class="card-btn">Quiz</ion-button><br><br>
    </ion-nav-link>
  </ion-content>
</template>
  
<script lang="ts">
  import { IonContent, IonHeader, IonTitle, IonToolbar, IonButton, alertController, IonNavLink } from '@ionic/vue';
  import { defineComponent } from 'vue';
  import QuizPage from './QuizPage.vue';
  import StudyPage from './StudyPage.vue';

  export default defineComponent({
    components: { IonContent, IonHeader, IonTitle, IonToolbar, IonButton, IonNavLink},
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
        studyPageComponent: StudyPage,
        quizPageComponent: QuizPage,
      };
    },     
  });
</script>