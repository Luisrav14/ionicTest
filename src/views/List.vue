<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title align="center">Lista | </ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-item-divider>
        <ion-label>Todas las canciones</ion-label>
      </ion-item-divider>
      <ion-list ref="closeSlidingItem">
        <ion-item-sliding v-for="el in lista" :key="el.key">
          <ion-item>
            <ion-label> {{ el.name }}</ion-label>
          </ion-item>
          <ion-item-options side="end">
            <ion-item-option @click="addFav(el), openToast(el.isFav ? 'Canción añadida a favoritos' : 'Canción eliminada de favoritos')">
              <ion-icon v-if="el.isFav" name="heart"></ion-icon>
              <ion-icon v-else name="heart-outline"></ion-icon>
            </ion-item-option>
          </ion-item-options>
        </ion-item-sliding>
      </ion-list>

      <ion-item-divider v-if="!!myFavorites[0]">
        <ion-label>Canciones favoritas</ion-label>
      </ion-item-divider>

      <ion-list>
        <ion-item v-for="el in myFavorites" :key="el.key">
          <ion-item>
            <ion-label> {{ el }}</ion-label>
          </ion-item>
        </ion-item>
      </ion-list>
    </ion-content>
  </ion-page>
</template>

<script>
import { IonPage, IonToolbar, toastController, IonContent, IonList, IonItem, IonLabel, IonTitle, IonHeader, IonItemSliding, IonItemOption, IonItemOptions, IonIcon } from "@ionic/vue";
import { defineComponent } from "vue";

export default defineComponent({
  name: "ListPage",
  components: {
    IonContent,
    IonList,
    IonItem,
    IonLabel,
    IonTitle,
    IonHeader,
    IonToolbar,
    IonPage,
    IonItemSliding,
    IonItemOption,
    IonItemOptions,
    IonIcon,
  },

  data() {
    return {
      lista: [
        { id: 1, name: "JGL", isFav: false },
        { id: 2, name: "Botones azules", isFav: false },
        { id: 3, name: "Side to side", isFav: false },
        { id: 4, name: "Imagine", isFav: false },
        { id: 5, name: "To My Love", isFav: false },
        { id: 6, name: "Amorfoda", isFav: false },
        { id: 7, name: "La MB", isFav: false },
        { id: 8, name: "Cielo rojo", isFav: false },
        { id: 9, name: "La llamarada", isFav: false },
        { id: 10, name: "Cuando calienta el sol", isFav: false },
        { id: 11, name: "Por debajo de la mesa", isFav: false },
        { id: 12, name: "La media vuelta", isFav: false },
        { id: 13, name: "Encadenados", isFav: false },
        { id: 14, name: "Yonaguni", isFav: false },
        { id: 15, name: "911", isFav: false },
      ],
      myFavorites: [],
    };
  },
  methods: {
    addFav: function (el) {
      if (!el.isFav) {
        this.myFavorites.push(el.name);
        el.isFav = true;
      } else {
        this.myFavorites = this.myFavorites.filter((item) => item !== el.name);
        el.isFav = false;
      }
      this.$refs.closeSlidingItem.$el.closeSlidingItems();
    },

    async openToast(msj) {
      const toast = await toastController.create({
        message: msj,
        duration: 2000,
      });
      return toast.present();
    },
  },
});
</script>
