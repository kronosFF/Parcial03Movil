<template>    
    <ion-card color="light" class="card">
        <div class="background-img">
            <img class="img" alt="Imagen de portada del anime" src="" />
        </div>
        <ion-card-header>
            <ion-card-title>
                <p class="title">
                    {{ animes.title.text }}
                </p>
            </ion-card-title>
            <ion-card-subtitle>
                <p class="prod">Productora</p>
                <p class="subtitle">
                    {{ animes.studio }}
                </p>
            </ion-card-subtitle>
        </ion-card-header>

        <ion-card-content>
            <p class="description">
                {{ animes.description }}
            </p>
        </ion-card-content>
        <div class="buttons">
            <div class="button">
                <ion-button color="light">
                    Descripción
                </ion-button>
            </div>
            <div class="button">
                <ion-button color="light">
                    Link Anime
                </ion-button>
            </div>
        </div>
    </ion-card>

    <!--Card de google-->

    <!--Card de google-->
</template>
  
<script lang="ts">
import { IonCard, IonButton, IonCardContent, IonCardHeader, IonCardSubtitle, IonCardTitle } from '@ionic/vue';
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'CardApp',
    components: { IonCard, IonButton, IonCardContent, IonCardHeader, IonCardSubtitle, IonCardTitle },

    props: {

        animes: {
            type: Object,
            default: {}
        },

        title: {
            type: String,
            default: '',
        },

        studio: {
            type: String,
            default: ''
        },

        description: {
            type: String,
            default: ''
        },

        image: {
            type: String,
            default: ''
        }

    },
    data() {
        return {
            base_img: '../assets/img/',
        }
    },

});
</script>

<style>
@import url(https://fonts.googleapis.com/css?family=Lato:400,700,900);

.card {
    border-radius: 14px;
    box-sizing: border-box;
    box-shadow: 3px 3px 20px rgba(0, 0, 0, .5);
}

.subtitle {
    text-transform: uppercase;
    font-size: 18px;
    font-weight: 900;
    color: #EE5487;
    margin: -2px;
    margin-bottom: -10px;
}

.prod {
    font-size: 8px;
    font-weight: 100;
}

.title {
    font-size: 23px;
    color: black;
    font-weight: 900;
}

.buttons {
    display: flex;
    flex-direction: row;
    background: #9f5b6f;
    height: 100px;
    width: 100%;
    justify-content: center;
    align-items: center;
}

.button {
    margin: 10px;
}

ion-button:hover {
    cursor: pointer;
}


.background-img {
    background: url('https://s3-us-west-2.amazonaws.com/s.cdpn.io/195612/coc-background.jpg');
}
</style>