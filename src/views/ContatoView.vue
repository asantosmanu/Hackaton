<script setup>
import { ref, computed } from 'vue'


const nome = ref('')
const email = ref('')
const senha = ref('')
const obs = ref('')
const confirma = ref('')
const ok = ref(false)




function validar() {
    if (senha.value === confirma.value) {
        return true;
    }
    else {
        return false;
    }
}
const mensagemErro = computed(() => {
    if (senha.value != confirma.value) {
        return 'As senhas devem ser iguais!'
    } else {
        return ''
    }
})




</script>
<template>
    <div class="row">
        <div class="banner">
            <div class="inner-text">
                <h1 class="titu">CONTATO</h1>
            </div>
        </div>
        <div class="titu2">
            <h1 class="CO">
                CONTATO
            </h1>
            <h3>Escolha um dos canais para que possamos responder o mais rápido possível.</h3>
        </div>


        <div class="contact-form">
            <form id="contact-form" action="index.html" method="get" enctype="multipart/form-data">

                <div class="info">
                    <h3 class="titu3">Informações de contato </h3>
                    <div>
                        <img class="img1" src="loc.png" alt="">
                        Av Do Principe, 1186, Itapema do Norte - Itapoá /SC
                    </div>
                    <div>
                        <img class="img1" src="caixa.png" alt="">
                        rfconsultoriaimobiliaria@outlook.com.br
                    </div>
                    <div>
                        <img class="img1" src="telefone2.png" alt="">
                        (47) 3443-3178
                    </div>
                    <div>
                        <img class="img1" src="wpp.png" alt="">
                        (47) 99684-3087
                    </div>
                </div>

                <!-- contato-formulario -->
                <div class="container-form">
                    <form class="form" @submit.prevent="ok = validar()">
                        <div class="centro">
                            <div class="dados">
                                <div class="nome">
                                <input type="text" v-on:keypress="ok = false" v-model="nome" required
                                    placeholder="Digite seu nome" />
                                </div>
                                <hr>
                                <div class="email">
                                <input type="email" v-on:keypress="ok = false" v-model="email"
                                    placeholder="Digite seu email" />
                                </div>
                                <hr>
                                <div class="telefoneCL">
                                    <input type="password" v-on:keypress="ok = false" v-model="senha" minlength="6"
                                        placeholder="Digite seu tele" />
                                </div>
                                <hr>
                                <div class="telefoneFX">
                                    <input type="password" v-on:keypress="ok = false" v-model="confirma" minlength="6"
                                        placeholder="Digite sua senha novamente" />
                                    <p class="paga">{{ mensagemErro }}</p>
                                </div>
                                <hr>
                                <input type="text" v-on:keypress="ok = false" v-model="obs" style="padding: 30px;"
                                    placeholder="Digite uma obs sobre a loja..." />
                                 <br>
                                <button class="comp" type="submit">Enviar</button>
                            </div>
                        </div>
                    </form>
                </div>
            </form>
        </div>
    </div>
</template>

<style scoped>

.nome{
    display: flex;
    flex-direction: column;
    align-items: baseline;
}
.email{
    margin-top: -6%;
    display: flex;
    flex-direction: column;
    align-items: end;
}

h2 {
    font-size: 25px;
}

.container-form {
    margin-left: 35%;
    margin-top: -15%;
}

.row {
    margin-right: -15px;
    margin-left: -15px;
}

.titu {
    color: white;
}

.titu2 {
    display: flex;
    flex-direction: column;
    align-items: center;

}

.titu3 {
    padding: 0 0 0 20px;
}

.info {
    margin-left: 8%;
    margin-top: 50px;
    display: flex;
    flex-direction: column;
    font-size: 14px;
    padding: 0 0 0 70px;
    list-style: none;
    padding-left: 40px;
    position: relative;
    margin-bottom: 20px;
    line-height: 22px;
    color: #535353;
}

.container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 90vh;
    color: white;
    border: 1px solid #ccc;
    transform: scale(0.7);
    padding-right: 15px;
    padding-left: 15px;
    margin-right: auto;
    margin-left: auto;

}

.form {
    max-width: 700px;
    padding: 25px;
    /* border: 1px solid #ccc; */
    /* background-color: #848486; */
    width: 85vh;
    font-family: 'Times New Roman', Times, serif;
    transform: scale(0.8);
    font-size: 22px;
}



.dados {
    font-family: Arial, Helvetica, sans-serif;
    /* color: black; */
}

.img1 {
    height: 38px;
    width: 45px;
}

.banner {
    border-radius: 0%;
    background: url(https://www.rafaelfonsecaimoveis.com.br/assets/img/anuncie/banner-anuncie.png) top left repeat;
    background-repeat: no-repeat;
    background-size: cover;
    background-size: cover;
    height: 280px;
    background-position: center center;
    background-repeat: no-repeat;
    position: relative;
    background-color: rgba(36, 42, 53, 0.7);
    /* color: aliceblue; */
    display: flex;
    align-items: center;
    flex-direction: column;
    /* padding: 100px 0 0 0 ; */
}

.inner-text {
    height: 100%;
    width: 100%;
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: center;
    background-color: black;
    opacity: 70%;
}

.CO {
    font-size: 25px;
    margin-top: 30px;
    color: #37404D;
}
</style>