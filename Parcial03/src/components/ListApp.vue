<template>
  <ion-page>
    <ion-content>
      <header>
        <div class="overlay">
          <h1>Ionic | Vue3</h1>
          <h3>Frameworks</h3>
        </div>
      </header>
      <swiper>
        <swiper pager="true">
          <swiper-slide v-for="(anime, index) in animes" :key="index">
            <CardApp :animes="anime" />
          </swiper-slide>
        </swiper>
      </swiper>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonPage, IonContent } from '@ionic/vue';
import { Swiper, SwiperSlide } from 'swiper/vue';
import animeData from '@/assets/Anime_Api.json';
import CardApp from './CardApp.vue';
import 'swiper/css';
import '@ionic/vue/css/ionic-swiper.css';

export default {

  components: { IonPage, Swiper, SwiperSlide, CardApp, IonContent },

  data() {
    return {
      animes: animeData,
    };
  },

};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Quicksand&display=swap');

/* Estilos del header */
header {
  background: url('http://www.autodatz.com/wp-content/uploads/2017/05/Old-Car-Wallpapers-Hd-36-with-Old-Car-Wallpapers-Hd.jpg');
  text-align: center;
  width: 100%;
  height: 130px;
  background-size: cover;
  background-attachment: fixed;
  position: absolute;
  overflow: hidden;
  border-radius: 0 85% / 30%;
  top: 1px;
  box-shadow: 0px 0px 10px #71127d;
}

header .overlay {
  width: 100%;
  height: 120%;
  padding: 1px;
  color: #FFF;
  text-shadow: 1px 1px 1px #333;
  /* background-image: linear-gradient(135deg, #9f05ff69 10%, #fd5e086b 100%); */
  background-image: linear-gradient(135deg, #e31d5f 10%, #fd5e086b 100%);

}

h1 {
  font-family: 'Poppins', 'sans-serif';
  font-size: 30px;
  margin-top: 30px;
}

h3 {
  font-family: 'Poppins', sans-serif;
  margin-bottom: 1px;
  font-size: 12px;
}

/* Fin estilos del header */
</style>