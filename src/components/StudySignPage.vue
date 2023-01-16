<template>
    <ion-header>
        <ion-toolbar>
        <ion-buttons slot="start">
            <ion-back-button></ion-back-button>
        </ion-buttons>
        <ion-title>Study Signs</ion-title>
        </ion-toolbar>
    </ion-header>
    <ion-content>
        <div v-for="index in dataCounts" :key="index" class="ion-text-center">        
            <ion-card>
                <h4 style="color: black;">No. {{ String(index).padStart(3, '0') }}</h4>
                <img :src="getImgPath(zeroPad(index,3))" style="width: 50%"/>
                <img :src="getImgPath(zeroPad(index,3) + 'w')" style="width: 75%"/>
            </ion-card>
        </div>
    </ion-content>
    </template>
    
    <script lang="ts">
        import signImg from '../../public/assets/imgs/signPath.json';
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
                dataCounts: signImg.dataCounts
              }
            },
            methods:{
                getImgPath(name: string){
                    return '/assets/imgs/sign/' + name + '.png';
                }
            }
        };
    </script>