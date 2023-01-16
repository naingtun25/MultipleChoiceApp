<template>
    <ion-header>
        <ion-toolbar>
        <ion-buttons slot="start">
            <ion-back-button></ion-back-button>
        </ion-buttons>
        <ion-title>Study Regulations</ion-title>
        </ion-toolbar>
    </ion-header>
    <ion-content>
        <div v-for="(slide, index) in slides" :key="index" class="ion-text-center">        
            <ion-card>
                <h1>{{slide.title}}</h1>
                <img :src="slide.img"/>
                <!-- <ion-card-header>
                    <ion-card-title>Card Title</ion-card-title>
                    <ion-card-subtitle>Card Subtitle</ion-card-subtitle>
                </ion-card-header> -->

                <ion-card-content>
                    Here's a small text description for the card content. Nothing more, nothing less.
                </ion-card-content>
            </ion-card>
        </div>
    </ion-content>
    </template>
    
    <script lang="ts">
        import imgSlides from '../../public/assets/imgs/signPath.json'
    
        import {
            IonHeader,
            IonTitle,
            IonToolbar,
            IonContent,
            IonButtons,
            IonBackButton,
        } from '@ionic/vue';
    
        export default {
            components: {
            IonHeader,
            IonTitle,
            IonToolbar,
            IonContent,
            IonButtons,
            IonBackButton,
            // IonItem,
            },
            data(){
              return{
                slides: JSON.parse(JSON.stringify(imgSlides) || '{}').slides
              }
            },
        };
    </script>