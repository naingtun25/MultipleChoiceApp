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
    <IonSlides style="height: 100%">
        <IonSlide v-for="(slide, index) in slides" :key="index">
          <IonCard class="center">
            <h1>{{slide.title}}</h1>
            <img :src="slide.img" style="width: 80%"/>
            <ion-card-header>
                <ion-card-subtitle>Destination</ion-card-subtitle>
                <ion-card-title>Madison, WI</ion-card-title>
            </ion-card-header>
            <ion-card-content>
                Founded in 1829 on an isthmus between Lake Monona and Lake Mendota, Madison was named the capital of the Wisconsin Territory in 1836.
            </ion-card-content>
            </IonCard>
        </IonSlide>
    </IonSlides>

</ion-content>
</template>

<script lang="ts">
    import imgSlides from '../../public/assets/imgs/studyCardPath.json'

    import {
        IonHeader,
        IonTitle,
        IonToolbar,
        IonContent,
        IonButtons,
        IonBackButton,
        IonCard,
        IonSlide,
        IonSlides,
    } from '@ionic/vue';

    export default {
        components: {
        IonHeader,
        IonTitle,
        IonToolbar,
        IonContent,
        IonButtons,
        IonBackButton,
        IonCard,
        IonSlide,
        IonSlides
        },
        data(){
          return{
            slides: JSON.parse(JSON.stringify(imgSlides) || '{}').slides
          }
        },
    };
</script>