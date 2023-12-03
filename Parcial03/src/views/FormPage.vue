<template>
  <ion-page>
    <!--Menu toggle-->
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-buttons slot="start">
          <ion-menu-button color="primary"></ion-menu-button>
        </ion-buttons>
        <ion-title>Contácto</ion-title>
      </ion-toolbar>
    </ion-header>
    <!--fin Menu toggle-->

    <ion-content :fullscreen="true">
      <div id="container">
      </div>
      <!--Componente del listado-->
      <FormApp class="listComponent"/>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonButtons, IonContent, IonHeader, IonMenuButton, IonPage, IonTitle, IonToolbar } from '@ionic/vue';
import FormApp from '@/components/FormApp.vue'
</script>

<style scoped>
.listComponent{
  text-align: center;
  position: absolute;
  left: 0;
  right: 0;
  top: 5%;
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  color: #8c8c8c;
  margin: 0;
}

#container a {
  text-decoration: none;
}
</style>
