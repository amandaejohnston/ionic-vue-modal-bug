<template>
  <ion-app>
    <ion-page>
      <ion-header class="ion-no-border">
        <ion-toolbar color="dark">
          <ion-title class="text-4xl font-extrabold font-handel"
            >PLUS</ion-title
          >
          <ion-buttons slot="end" @click="presentActionSheet()">
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
      <ion-content class="ion-padding">
        <ion-card>
          <ion-card-header>
            State management of the store by dispatching action to change value
            in store, no payload passed
          </ion-card-header>
          <ion-card-content>
            <ion-item>
              {{ theCount }}
            </ion-item>
            <ion-button @click="goUp">UP</ion-button>
            <ion-button @click="goDown">down</ion-button>
          </ion-card-content>
        </ion-card>
        <ion-card>
          <ion-card-header>
            State management of the store by dispatching action to change value
            in store, using the payload passed in my the component
          </ion-card-header>
          <ion-card-content>
            <ion-item>
              <ion-input type="number" v-model="newValue"></ion-input>
            </ion-item>
            <ion-button @click="onChangeTo">Change To</ion-button>
          </ion-card-content>
        </ion-card>
      </ion-content>
    </ion-page>
  </ion-app>
</template>

<script lang="ts">
import { computed, defineComponent, ref } from "vue";
import {
  IonApp,
  IonPage,
  IonHeader,
  IonToolbar,
  IonTitle,
  IonButton,
  IonItem,
  IonCardContent,
  IonCard,
  IonCardHeader,
  IonButtons,
  IonContent,
  IonInput,
  modalController,
} from "@ionic/vue";
import { useStore } from "vuex";
import Modal from "@/components/Modal.vue";

export default defineComponent({
  name: "App",
  components: {
    IonApp,
    IonPage,
    IonHeader,
    IonCardContent,
    IonCard,
    IonCardHeader,
    IonToolbar,
    IonButtons,
    IonTitle,
    IonButton,
    IonItem,
    IonContent,
    IonInput,
  },
  setup(props, ctx) {
    const store = useStore();
    const newValue = ref<string>("0");

    const presentActionSheet = async () => {
      const modal = await modalController.create({
        component: Modal,
      });
      return modal.present();
    };

    const onChangeTo = () => {
      store.dispatch("changeTo", { value: parseInt(newValue.value) });
    };
    return {
      newValue,
      onChangeTo,
      presentActionSheet,
      theCount: computed(() => store.state.count),
      goUp: () => store.dispatch("up"),
      goDown: () => store.dispatch("down"),
    };
  },
});
</script>

<style>
</style>
