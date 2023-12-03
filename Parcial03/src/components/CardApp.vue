<template>
    <section>
        <div class="container">
            <div class="content">
                <ion-card class="card">
                    <ion-card-content class="card-content">
                        <div class="image">
                            <img src="../assets/img/Battle_Spirits__Double_Drive.jpg" alt="icon-anime">
                        </div>
                        <div class="media-icons">
                            <a href="https://web.facebook.com/profile.php?id=100004216729178">
                                <i class="fa-brands fa-facebook"></i>
                            </a>
                            <a href="https://www.instagram.com/yeison_andres_lopez/">
                                <i class="fa-brands fa-instagram"></i>
                            </a>
                            <a href="https://github.com/kronosFF" target="_blank">
                                <i class="fa-brands fa-github"></i>
                            </a>
                        </div>
                        <div class="name profession">
                            <span class="name">{{ animes.title.text }}</span>
                            <span class="profession">{{ animes.description }}</span>
                        </div>
                        <div class="rating">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="far fa-star"></i>
                        </div>
                        <div class="button">
                            <button class="detail" @click="openAlertDialog">Detalle</button>
                            <button class="detail" @click="linkAnime">Visitar</button>
                            <button class="detail" @click="getGenres">Géneros</button>
                        </div>
                    </ion-card-content>
                </ion-card>
            </div>
        </div>
    </section>
</template>
  
<script lang="ts">
import { IonCard, alertController, IonButton, IonCardContent, IonCardHeader, IonCardSubtitle, IonCardTitle } from '@ionic/vue';
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'CardApp',
    components: { IonCard, IonButton, IonCardContent, IonCardHeader, IonCardSubtitle, IonCardTitle },

    methods: {
        async openAlertDialog() {
            const a = await alertController
                .create(
                    {
                        header: this.animes.title.text,
                        message: this.animes.description,
                        buttons: ['Cerrar']
                    }
                );
            await a.present();
        },

        linkAnime(){
            if (this.animes && this.animes.title.link){
                window.open(this.animes.title.link, '_blank');
            }
        },

        async getGenres() {
            const a = await alertController
                .create(
                    {
                        header: this.animes.title.text,
                        message: this.animes.genres,
                        buttons: ['Cerrar']
                    }
                );
            await a.present();
        },

    },

    props: {

        animes: {
            type: Object,
            default: {}
        },

    },
    data() {
        return {
            base_img: '../assets/img/',
        }
    },

});
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Quicksand&display=swap');


/*Estilos de card*/

section .card .image {
    height: 240px;
    width: 240px;
    border-radius: 50%;
    padding: 3px;
    background-color: #EE5487;
}

section .card .image img {
    height: 100%;
    width: 100%;
    object-fit: cover;
    border-radius: 50%;
    border: 3px solid #fff;
}

section {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Poppins', 'sans-serif';
    margin-top: 30px;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
}

.card {
    background: #fff;
    border-radius: 0 45% / 7%;
    margin: 20px 0;
    height: 550px;
}

.card::before {
    content: "";
    position: absolute;
    height: 30%;
    width: 330px;
    background: #EE5487;
    border-radius: 0 0 85% 85% / 30%;
}

.card .card-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 30px;
    position: relative;
    z-index: 100;
}

.card .media-icons {
    position: absolute;
    top: 10px;
    left: 30px;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.card .media-icons i {
    color: #fff;
    opacity: 0.6;
    margin-top: 10px;
    transition: all 0.3s ease;
    cursor: pointer;
}

.card .media-icons i:hover {
    opacity: 1;
}

.card .name-profession {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 10px;
    color: #333;
}

.name {
    font-size: 20px;
    font-weight: 600;
    margin-top: 10px;
    color: #e31d5f;
}

.profession {
    overflow: hidden;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 3;
    font-size: 15px;
    font-weight: 500;
    margin-top: 20px;
    color: #333;
}

.card .rating {
    display: flex;
    align-items: center;
    margin-top: 18px;
}

.card .rating i {
    font-size: 19px;
    margin: 0 4px;
    color: #EE5487;
}

.card .button {
    width: 100%;
    display: flex;
    justify-content: space-around;
    margin-top: 20px;
}

.card .button button {
    background: #EE5487;
    outline: none;
    border: none;
    color: #fff;
    padding: 14px 22px;
    border-radius: 14px;
    font-size: 14px;
    transition: all 0.3s ease;
    cursor: pointer;
}

.button button:hover {
    background-color: #e31d5f;
}

/*Fin estilos de card*/
</style>