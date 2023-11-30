<template>
  <ion-page>
    <ion-grid>
      <ion-row>
        <ion-col>
          <CardApp v-for="anime in animes" :key="anime.hype" 
                  :animes="anime" />
        </ion-col>
      </ion-row>
    </ion-grid>
  </ion-page>
</template>

<script lang="ts">
import { IonGrid, IonRow, IonCol } from '@ionic/vue';
import anime from '@/assets/Anime_Api.json'
import CardApp from './CardApp.vue';

interface Anime {
  studio: string;
  genres: string[];
  hype: number;
  description: string;
  title: {
    link: string;
    text: string;
    img: string;
  };
  start_date: string;
}

export default {
  name: 'ListApp',

  components: { CardApp },

  computed: {
    animes() {
      return this.limitarDescripcion(anime.map(anime => ({ ...anime } as Anime)));
    },
  },

  methods: {
    limitarDescripcion(object: Anime[]) {
      anime.forEach(Anime => {
        if (Anime.description) {
          let palabras = Anime.description.split(' ');

          let primera20Palabras = palabras.slice(0, 20);

          let nuevaDescripcion = primera20Palabras.join(' ');

          Anime.description = nuevaDescripcion + '...';
        }
      });

      return anime;
    },
  },


  
}
</script>
