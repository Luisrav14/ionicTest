<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title align="center">Lista | Canciones</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-item-divider>
        <ion-label> Todas las canciones </ion-label>
      </ion-item-divider>
      <ion-list style="" ref="closeSlidingRef">
        <ion-item-sliding v-for="el in list" :key="el.id">
          <ion-item>
            <ion-label>{{ el.id }}.- {{ el.name }}</ion-label>
          </ion-item>
          <ion-item-options side="end">
            <ion-item-option @click="addFav(el)">
              <ion-icon v-if="this.myFavs.find((item) => item.id == el.id)" name="heart"></ion-icon>
              <ion-icon v-else name="heart-outline"></ion-icon>
            </ion-item-option>
          </ion-item-options>
        </ion-item-sliding>
      </ion-list>
      <ion-item-divider>
        <ion-label>Canciones Favoritas</ion-label>
      </ion-item-divider>
      <ion-list style="margin-buttom: 2em" ref="">
        <ion-item-sliding v-for="fav in myFavs" :key="fav.id">
          <ion-item>
            <ion-label>{{ fav.id }}.- {{ fav.name }}</ion-label>
          </ion-item>
          <ion-item-options side="end">
            <ion-item-option @click="addFav(el)"><ion-icon name="heart"></ion-icon></ion-item-option>
          </ion-item-options>
        </ion-item-sliding>
      </ion-list>
    </ion-content>
  </ion-page>
</template>

<script>
import { defineComponent } from "vue";

import { IonItem, IonList, IonLabel } from "@ionic/vue";

export default defineComponent({
  name: "ListPage",
  components: {
    IonItem,
    IonList,
    IonLabel,
  },
  data: function () {
    return {
      list: [
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
      myFavs: [],
    };
  },
  methods: {
    addFav: function (el) {
      if (!this.myFavs.find((item) => item.id == el.id)) {
        this.myFavs.push(el);
        console.log(el);
      } else {
        this.myFavs.find((item) => item.id == el.id);
      }
      this.$refs.closeSlidingRef.$el.closeSlidingItems();
    },
  },
});
</script>
