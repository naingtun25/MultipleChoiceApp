<template>
  <ion-header>
    <ion-toolbar>
    <ion-buttons slot="start">
        <ion-back-button @click="onBackButtonClick"></ion-back-button>
    </ion-buttons>
    <ion-title>Choice Letter</ion-title>
    </ion-toolbar>
  </ion-header>

  <ion-content color="gradient2" class="ion-padding ion-text-center">
    <ion-item color="transparent" lines="none">
      <img src="../../public/assets/imgs/car1.png" class="center round-border-img"/>
    </ion-item><br>
    <ion-radio-group v-model="selectedValue" ref="radioGroup">
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
    </ion-radio-group><br>
    <ion-button @click="onSubmitButtonClick" shape="round" color="dark">အိုကေ</ion-button>
  </ion-content>
</template>
  
<script>    
    let score = 1;
    import { defineComponent } from 'vue';
    import { IonHeader, IonTitle, IonToolbar, IonContent, IonButtons, IonBackButton, IonRadioGroup, IonRadio, IonItem, alertController, toastController } from '@ionic/vue';
  
    export default defineComponent({
      components: { IonHeader, IonTitle, IonToolbar, IonContent, IonButtons, IonBackButton, IonRadioGroup, IonRadio, IonItem },
      data() {
        return {
          selectedValue: '0'
        }
      },
      methods: {
       async onSubmitButtonClick() {
          if(this.selectedValue == '0'){
            this.presentToast();
            return;
          }
          let headerMessage = 'မှားသည်';
          let subHeaderMessage = 'အဖြေမှန်: ' + this.selectedValue;
          const scoreMessage = 'ရမှတ်: ' + score;
          if(this.selectedValue != '0'){
            headerMessage = 'မှန်သည်';
            subHeaderMessage = '';
            score = score + 1;
          }
          const alert = await alertController.create({
            header: headerMessage,
            subHeader: subHeaderMessage,
            message: scoreMessage,
            buttons: [
              {
                text: 'နောက်သို့',
                role: 'confirm',
                handler: () => {
                  this.nextHandler();
                },
              },
            ],            
            backdropDismiss: false,
          });
          await alert.present();
        },
        nextHandler(){
          console.log('next');
          this.selectedValue = '0';
        },
        onBackButtonClick() {
          score = 1;
        },
        async presentToast() {
          const toast = await toastController.create({
            message: 'ကျေးဇူးပြု၍ အဖြေရွေးပါ',
            duration: 1000,
            position: 'bottom'
          });
          await toast.present();
        },
      },
    })
</script>