<template>
  <ion-header>
    <ion-toolbar>
      <ion-title>Home</ion-title>
    </ion-toolbar>
  </ion-header>
  
  <ion-content class="ion-padding">
    <div class="container">
      <div class="content-center">
        <ion-nav-link router-direction="forward" :component="studyPageComponent">        
          <ion-button color="light" shape="round" class="card-btn">Study</ion-button><br><br>
        </ion-nav-link>
        <ion-nav-link router-direction="forward" :component="mockTestsPageComponent">        
          <ion-button color="light" shape="round" class="card-btn">Mock Tests</ion-button><br><br>
        </ion-nav-link>
      </div>
    </div>
  </ion-content>
</template>
  
<script lang="ts">
  import { IonContent, IonHeader, IonTitle, IonToolbar, IonButton, IonNavLink } from '@ionic/vue';
  import { defineComponent } from 'vue';
  import StudyPage from './StudyPage.vue';
  import MockTestsPage from './MockTestsPage.vue';
  
  export default defineComponent({
    components: { IonContent, IonHeader, IonTitle, IonToolbar, IonButton, IonNavLink},
    data() {
      return {
        studyPageComponent: StudyPage,
        mockTestsPageComponent: MockTestsPage,
      };
    },     
  });
</script>