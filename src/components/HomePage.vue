<template>
  <ion-header>
    <ion-toolbar>
      <ion-title>Home</ion-title>
    </ion-toolbar>
  </ion-header>
  
  <ion-content style="text-align: center;" class="ion-padding">
    <div class="container">
      <div class="content-center">
        <ion-nav-link router-direction="forward" :component="studyPageComponent">        
          <ion-button color="gradient3" shape="round" class="card-btn">Study</ion-button><br><br>
        </ion-nav-link>
        <ion-nav-link router-direction="forward" :component="multipleChoicePageComponent">        
          <ion-button color="gradient3" shape="round" class="card-btn">Multiple Choice</ion-button><br><br>
        </ion-nav-link>
      </div>
    </div>
  </ion-content>
</template>
  
<script lang="ts">
  import { IonContent, IonHeader, IonTitle, IonToolbar, IonButton, alertController, IonNavLink } from '@ionic/vue';
  import { defineComponent } from 'vue';
  import StudyPage from './StudyPage.vue';
  import MultipleChoicePage from './MultipleChoicePage.vue';
  
  export default defineComponent({
    components: { IonContent, IonHeader, IonTitle, IonToolbar, IonButton, IonNavLink},
    data() {
      return {
        studyPageComponent: StudyPage,
        multipleChoicePageComponent: MultipleChoicePage,
      };
    },     
  });
</script>