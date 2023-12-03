<template>
    <!--Contenido del header-->
    <header>
        <div class="overlay">
            <h1>Ionic | Vue3</h1>
            <h3>Frameworks</h3>
        </div>
    </header>
    <!--Fin contenido del header-->
    <section>
        <div class="container">
            <div class="content">
                <IonCard class="card">
                    <ion-card-content>
                        <div class="name-profession">
                            <span class="yeison">Yeison Lopez</span>
                            <span class="title-form">Formulario de Registro</span>
                        </div>

                        <form action="">
                            <div class="mb-3">
                                <label for="" class="form-label">Nombre</label>
                                <input type="text" class="form-control" aria-describedby="emailHelp">
                            </div>
                            <div class="mb-3">
                                <label for="" class="form-label">Apellido</label>
                                <input type="text" class="form-control" aria-describedby="emailHelp">
                            </div>
                            <div class="mb-3">
                                <label for="" class="form-label">Correo Electrónico</label>
                                <input type="email" class="form-control" aria-describedby="emailHelp">
                                <div id="emailHelp" class="form-text">Nunca compartiremos su correo electrónico con nadie más.
                                </div>
                            </div>
                            <div class="mb-3">
                                <label for="" class="form-label">Déjanos Tus Comentarios</label>
                                <textarea class="form-control" name="" id="" cols="30" rows="10"></textarea>
                            </div>
                        </form>
                        <div class="button">
                            <button class="detail">Enviar</button>
                        </div>
                    </ion-card-content>
                </IonCard>
            </div>
        </div>
    </section>
</template>

<script lang="ts">
import { IonPage, IonContent, IonCard, IonCardContent, IonCardHeader, IonCardTitle, IonCardSubtitle } from '@ionic/vue';
import { defineComponent } from 'vue';

export default defineComponent({
    components: { IonCard, IonCardContent, IonCardHeader, IonContent, IonPage, IonCardTitle, IonCardSubtitle }
})

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
    top: 45px;
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

/*Estilos de contenido*/


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
    height: 900px;
    margin-top: 400px;
}

.card::before {
    content: "";
    position: absolute;
    height: 20%;
    width: 100%;
    background: #EE5487;
    border-radius: 0 5 85% / 30%;
}


.card .card-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 30px;
    position: relative;
    z-index: 100;
}

label {
    color: #333;
    font-size: 20px;
    margin-top: 10px;
}

.card-header {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 50px;
    font-family: 'Poppins', 'sans-serif';
    margin-top: 20px;
}

.card .name-profession {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 20px;
    position: relative;
    margin-bottom: 40px;
}

.title-form {
    font-size: 35px;
    font-weight: 600;
    color: #f3f3f3;
    text-align: center;
    letter-spacing: 2px;
    font-family: 'Poppins', 'sans-serif';
}

.yeison{
    color: #f3f3f3;
    font-size: 12px;
    font-family: 'Poppins', 'sans-serif';
}


.card .button {
    width: 100%;
    display: flex;
    justify-content: space-around;
    margin-top: 10px;
}

.card .button button {
    background: #EE5487;
    outline: none;
    border: none;
    color: #fff;
    padding: 14px 22px;
    border-radius: 14px;
    font-size: 20px;
    transition: all 0.3s ease;
    cursor: pointer;
}

.button button:hover {
    background-color: #e31d5f;
}

/*Fin estilos de contenido*/
</style>