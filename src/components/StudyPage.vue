<template>
<ion-header>
    <ion-toolbar>
    <ion-buttons slot="start">
        <ion-back-button></ion-back-button>
    </ion-buttons>
    <ion-title>Study</ion-title>
    </ion-toolbar>
</ion-header>
<ion-content class="ion-padding">
    <ion-nav-link router-direction="forward" :component="studyRegulationPageComponent">        
        <ion-item button detail lines="none" class="ion-item-border">
            <ion-label>Regulations</ion-label>
            <!-- <img src="../../public/assets/imgs/word.png"/> -->
        </ion-item>
    </ion-nav-link><br>
    <ion-nav-link router-direction="forward" :component="studySignPageComponent">        
        <ion-item button detail lines="none" class="ion-item-border">
            <!-- <img src="../../public/assets/imgs/word.png"/> -->
            <ion-label>Signs</ion-label>
        </ion-item>
    </ion-nav-link>
</ion-content>
</template>

<script lang="ts">
    import StudyRegulationPage from './StudyRegulationPage.vue';
    import StudySignPage from './StudySignPage.vue';

    import {
        IonHeader,
        IonTitle,
        IonToolbar,
        IonContent,
        IonButtons,
        IonBackButton,
        IonItem,
        IonLabel,
        IonNavLink
    } from '@ionic/vue';

    export default {
        components: {
        IonHeader,
        IonTitle,
        IonToolbar,
        IonContent,
        IonButtons,
        IonBackButton,
        IonItem,
        IonLabel,
        IonNavLink
        },
        data(){
          return{
            studyRegulationPageComponent: StudyRegulationPage,
            studySignPageComponent: StudySignPage,
          }
        },
    };
</script>