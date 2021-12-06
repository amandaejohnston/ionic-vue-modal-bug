<template>
  <ion-page>
    <ion-header class="ion-no-border">
      <ion-toolbar color="dark">
        <ion-title class="text-4xl font-extrabold font-handel">PLUS</ion-title>
        <ion-buttons slot="end" @click="close()">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            aria-hidden="true"
            focusable="false"
            data-prefix="fas"
            data-icon="times"
            width="24"
            class="mr-3"
            height="24"
            fill="gray"
            role="img"
            viewBox="0 0 352 512"
          >
            <path
              fill="currentColor"
              d="M242.72 256l100.07-100.07c12.28-12.28 12.28-32.19 0-44.48l-22.24-22.24c-12.28-12.28-32.19-12.28-44.48 0L176 189.28 75.93 89.21c-12.28-12.28-32.19-12.28-44.48 0L9.21 111.45c-12.28 12.28-12.28 32.19 0 44.48L109.28 256 9.21 356.07c-12.28 12.28-12.28 32.19 0 44.48l22.24 22.24c12.28 12.28 32.2 12.28 44.48 0L176 322.72l100.07 100.07c12.28 12.28 32.2 12.28 44.48 0l22.24-22.24c12.28-12.28 12.28-32.19 0-44.48L242.72 256z"
            />
          </svg>
        </ion-buttons>
      </ion-toolbar>
    </ion-header>
    <ion-content color="dark" fullscreen>
      <ion-list>
        <ion-list-header color="medium"> Sound </ion-list-header>
        <ion-item color="dark">
          <ion-buttons slot="end">
            <ion-toggle color="primary"></ion-toggle>
          </ion-buttons>
          <ion-label class="my-6 font-extrabold">Sound</ion-label>
        </ion-item>
        <ion-item color="dark">
          <ion-note slot="end" color="primary">yoyo</ion-note>
          <ion-label class="my-6 font-extrabold">Style</ion-label>
        </ion-item>

        <ion-item color="dark">
          <ion-buttons slot="end">
            <ion-toggle color="primary"></ion-toggle>
          </ion-buttons>
          <ion-label class="my-6 font-extrabold">Ticking sound</ion-label>
        </ion-item>
        <ion-list-header color="medium"> Helpers </ion-list-header>
        <ion-item color="dark">
          <ion-buttons slot="end">
            <ion-toggle color="primary"></ion-toggle>
          </ion-buttons>
          <ion-label class="my-6 font-extrabold">FlashLight</ion-label>
        </ion-item>
        <ion-item color="dark">
          <ion-buttons slot="end">
            <ion-toggle color="primary"></ion-toggle>
          </ion-buttons>
          <ion-label class="my-6 font-extrabold">Screen flash</ion-label>
        </ion-item>
      </ion-list>
      <ion-list>
        <ion-list-header color="medium"> Other </ion-list-header>
        <ion-item color="dark">
          <ion-label class="my-6 font-extrabold">Suggest</ion-label>
        </ion-item>
        <ion-item color="dark">
          <ion-label class="my-6 font-extrabold">Help</ion-label>
        </ion-item>
        <ion-item color="dark">
          <ion-label class="my-6 font-extrabold">Subscribe</ion-label>
        </ion-item>
        <ion-item color="dark">
          <ion-label class="my-6 font-extrabold">Restore</ion-label>
        </ion-item>
      </ion-list>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import {
  IonContent,
  IonPage,
  IonRange,
  IonItem,
  IonLabel,
  IonHeader,
  IonTitle,
  IonListHeader,
  IonNote,
  IonToggle,
  IonIcon,
  IonToolbar,
  IonList,
  IonButtons,
  modalController,
} from "@ionic/vue";
import { defineComponent } from "vue";
export default defineComponent({
  name: "App",
  components: {
    IonContent,
    IonPage,
    IonRange,
    IonItem,
    IonLabel,
    IonHeader,
    IonTitle,
    IonListHeader,
    IonNote,
    IonToggle,
    IonIcon,
    IonToolbar,
    IonList,
    IonButtons,
  },
  setup(props, ctx) {
    const close = () => {
      modalController.dismiss();
    };
    return {
      close,
    };
  },
});
</script>

<style lang="scss" scoped>
ion-toggle {
  --background: white;

  --handle-background: var(--ion-color-primary);
  --handle-background-checked: #000;
}
</style>
