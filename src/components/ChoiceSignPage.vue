<template>
  <ion-header>
    <ion-toolbar>
    <ion-buttons slot="start">
        <ion-back-button @click="onBackButtonClick"></ion-back-button>
    </ion-buttons>
    <ion-title>Choice Sign</ion-title>
    </ion-toolbar>
  </ion-header>

  <ion-content class="ion-padding ion-text-center">
    <h3>No. {{ problemNum }} </h3>
    <p>{{ generateChoiceProblem() }}</p>
    <ion-radio-group v-model="selectedValue" ref="radioGroup">
      <ion-item color="transparent" lines="none">
        <img :src="problems[problemNum-1].signPath" class="center round-border-img" style="width: 65%"/>
      </ion-item><br>
      <ion-item color="transparent" class="center ion-item-border" lines="none" style="width: 80%">
        <img src="../../public/assets/imgs/sign/001w.png"/>
        <ion-radio slot="end" mode="md" value="1"></ion-radio>
      </ion-item><br>
      <ion-item color="transparent" class="center ion-item-border" lines="none"  style="width: 80%">
        <img src="../../public/assets/imgs/sign/002w.png"/>
        <ion-radio slot="end" mode="md" value="2"></ion-radio>
      </ion-item><br>
      <ion-item color="transparent" class="center ion-item-border" lines="none"  style="width: 80%">
        <img src="../../public/assets/imgs/sign/003w.png"/>
        <ion-radio slot="end" mode="md" value="3"></ion-radio>
      </ion-item><br>
      <ion-item color="transparent" class="center ion-item-border" lines="none"  style="width: 80%">
        <img src="../../public/assets/imgs/sign/005w.png"/>
        <ion-radio slot="end" mode="md" value="4"></ion-radio>
      </ion-item>
    </ion-radio-group><br>
    <ion-button @click="onSubmitButtonClick" shape="round" color="dark">အိုကေ</ion-button>
  </ion-content>
</template>
  
<script>    
    let score = 1;
    import { defineComponent } from 'vue';
    import { IonHeader, IonTitle, IonToolbar, IonContent, IonButtons, IonBackButton, IonRadioGroup, IonRadio, IonItem, alertController, toastController } from '@ionic/vue';
    import signImg from '../../public/assets/imgs/signPath.json';

    export default defineComponent({
      components: { IonHeader, IonTitle, IonToolbar, IonContent, IonButtons, IonBackButton, IonRadioGroup, IonRadio, IonItem },
      data() {
        return {
          selectedValue: '0',
          dataCounts: signImg.dataCounts,
          problemNum: 1,
          problems: []
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
          this.selectedValue = '0';
          this.problemNum += 1;
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
        generateChoiceProblem(){
          this.problems.splice(0);
          for(let i = 1; i <= this.dataCounts; i++){
            const json = {
              sn: i,
              signPath: '/assets/imgs/sign/' + String(i).padStart(3, '0') + '.png',
              choice1Path: '',
              choice2Path:'',
              choice3Path:'',
              choice4Path:'',
              rightAns: 1
            }
            this.problems.push(json);
          }
          console.log(this.problems);
        }
      },
    })
</script>