<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-buttons slot="start">
          <ion-back-button default-href="/home"></ion-back-button>
        </ion-buttons>
        <ion-title>New Item</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content>
      <ion-icon :ios="logoApple" :md="logoAndroid"></ion-icon>
      <ion-button @click="scrollToBottom">Scroll to Bottom</ion-button>
      <ion-icon :icon="heart"></ion-icon>
    </ion-content>
  </ion-page>
</template>

<script>
import {
  IonBackButton,
  IonButtons,
  IonContent,
  IonHeader,
  IonPage,
  IonTitle,
  IonToolbar
} from '@ionic/vue';
  import { defineComponent, ref } from 'vue';
  import { heart, logoAndroid, logoApple } from 'ionicons/icons';

export default defineComponent({
  name: 'NewItem',
  components: {
    IonBackButton,
    IonButtons,
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar
  },
  setup() {
      const content = ref();
      const scrollToBottom = () => {
        content.value.$el.scrollToBottom(300);
      }

      return { content, scrollToBottom, heart, logoAndroid, logoApple }
  }
});
</script>