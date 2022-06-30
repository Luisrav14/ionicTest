<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title align="center">Canciones cards</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-card v-for="song in lista" :key="song.id">
        <ion-card-header>
          <div :style="{ backgroungImage: 'url(' + song.front + ')' }">
            <ion-img style="max-width: 85%; display: block; margin: 0 auto" :src="song.front"></ion-img>
          </div>
          <ion-fab vertical="end" horizontal="end" style="margin-top: -2em; margin-right: 1em">
            <ion-fab-button>
              <ion-icon name="add"></ion-icon>
            </ion-fab-button>
          </ion-fab>
          <ion-card-subtitle style="margin-bottom: -8px">{{ song.artist }}</ion-card-subtitle>
          <div class="container-song" style="display: flex; align-items: center; justify-content: space-between; margin-top: 1em">
            <ion-card-title class=""> {{ song.name }} </ion-card-title>
            <ion-card-subtitle style="font-size: 12px; backgorund-color: #a1a1a1; border-radius: 5px; margin-color: #f1f1f1">{{ song.duration }} </ion-card-subtitle>
          </div>
          <ion-card-subtitle class="" style="font-size: 12px">{{ song.year }} </ion-card-subtitle>
        </ion-card-header>
        <ion-card-content> Keep close to Nature's heart... and break clear away, once in awhile, and climb a mountain or spend a week in the woods. Wash your spirit clean. </ion-card-content>
      </ion-card>
    </ion-content>
  </ion-page>
</template>

<script>
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonCard, IonImg, IonIcon } from "@ionic/vue";

import { defineComponent } from "vue";

export default defineComponent({
  name: "CardPage",
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar,
    IonCard,
    IonImg,
    IonIcon,
  },

  data() {
    return {
      lista: [
        { id: 1, name: "JGL", isFav: false, front: "https://i.scdn.co/image/ab67616d0000b273deb46423294da327d2246acd", duration: "3:12", year: "2022", artist: "La Adictiva Ft. Luis R. Conriquez" },
        { id: 2, name: "Botones azules", isFav: false, front: "https://i.scdn.co/image/ab67616d0000b273f0aa183c41ae765922dc9eb7", duration: "3:12", year: "2022", artist: "Junior H Ft. Luis R Conriquez " },
        { id: 3, name: "Side to side", isFav: false, front: "https://lastfm.freetls.fastly.net/i/u/770x0/4e431f0a7e3ac21395e62995a4d02716.jpg", duration: "3:47", year: "2019", artist: "Ariana Grande Ft. Nicky Minaj" },
        { id: 4, name: "Imagine", isFav: false, front: "https://i1.sndcdn.com/artworks-000017289777-n5qjf4-t500x500.jpg", duration: "3:12", year: "1978", artist: "John Lennon" },
        { id: 5, name: "To My Love", isFav: false, front: "https://i.scdn.co/image/ab67616d0000b273deb46423294da327d2246acd", duration: "3:12", year: "2022", artist: "Artist" },
        { id: 6, name: "Amorfoda", isFav: false, front: "https://i.scdn.co/image/ab67616d0000b273deb46423294da327d2246acd", duration: "3:12", year: "2022", artist: "Artist" },
        { id: 7, name: "La MB", isFav: false, front: "https://i.scdn.co/image/ab67616d0000b273deb46423294da327d2246acd", duration: "3:12", year: "2022", artist: "Artist" },
        { id: 8, name: "Cielo rojo", isFav: false, front: "https://i.scdn.co/image/ab67616d0000b273deb46423294da327d2246acd", duration: "3:12", year: "2022", artist: "Artist" },
        { id: 9, name: "La llamarada", isFav: false, front: "https://i.scdn.co/image/ab67616d0000b273deb46423294da327d2246acd", duration: "3:12", year: "2022", artist: "Artist" },
        { id: 10, name: "Cuando calienta el sol", isFav: false, front: "https://i.scdn.co/image/ab67616d0000b273deb46423294da327d2246acd", duration: "3:12", year: "2022", artist: "Artist" },
        { id: 11, name: "Por debajo de la mesa", isFav: false, front: "https://i.scdn.co/image/ab67616d0000b273deb46423294da327d2246acd", duration: "3:12", year: "2022", artist: "Artist" },
        { id: 12, name: "La media vuelta", isFav: false, front: "https://i.scdn.co/image/ab67616d0000b273deb46423294da327d2246acd", duration: "3:12", year: "2022", artist: "Artist" },
        { id: 13, name: "Encadenados", isFav: false, front: "https://i.scdn.co/image/ab67616d0000b273deb46423294da327d2246acd", duration: "3:12", year: "2022", artist: "Artist" },
        { id: 14, name: "Yonaguni", isFav: false, front: "https://i.scdn.co/image/ab67616d0000b273deb46423294da327d2246acd", duration: "3:12", year: "2022", artist: "Artist" },
        { id: 15, name: "911", isFav: false, front: "https://i.scdn.co/image/ab67616d0000b273deb46423294da327d2246acd", duration: "3:12", year: "2022", artist: "Artist" },
      ],
      myFavorites: [],
    };
  },
});
</script>
