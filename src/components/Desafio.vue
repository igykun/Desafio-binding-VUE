<template>
<div id="app">
    <div>
        <form>
            <div>
                <label>Título de la tarjeta: </label>
                <input v-model="titulo"/>
            </div>

            <div>
                <label>Chip SRC: </label>
                <select v-model="chip">
                    <option disabled selected>Elige uno</option>
                    <option value="./src/assets/img/chip.png">/assets/chip.png</option>
                    <!-- opcion vacia para quitar la imagen -->
                    <option value="">nada</option>
                </select>
            </div>

            <div>
                <label>Número: </label>
                <input v-model="numero"/>
            </div>

            <div id="contenedorFecha">
                <label>Fecha de expiración: </label>
                <!-- hice dos, una para el mes y otra para el año, asi me sale en Mercado Libre -->
                <input class="fecha" v-model="fechaMes" maxlength="2" placeholder="mm"/>/<input class="fecha" v-model="fechaAno" maxlength="2" placeholder="aa"/>
            </div>

            <div>
                <label>Propietario: </label>
                <input type="text" v-model="nombre"/>
            </div>

            <div>
                <label>Tipo de tarjeta SRC: </label>
                <select v-model="tipoTarjeta">
                    <option disabled selected>Elige uno</option>
                    <option value="./src/assets/img/visa.png">/assets/visa.png</option>
                    <!-- opcion vacia para quitar la imagen -->
                    <option value="">nada</option> 
                </select>
            </div>
        </form>

        <div class="carnet">
            <h3>{{titulo}}</h3>
            <img width="40" :src="chip" alt="" />
            <div>
                <h2>{{ numero }}</h2>
                <span>Fecha Exp: <b>{{fechaMes}}/{{ fechaAno }}</b></span>
            </div>
            <footer>
                <span>{{nombre}}</span>
                <img :src="tipoTarjeta" width="60" />
            </footer>
        </div>
    </div>
</div>
</template>
<script>
export default {
    name: "carnet",
    data(){
        return{
            titulo: "",
            chip: "",
            numero: "",
            fechaMes: "",
            fechaAno: "",
            nombre: "",
            tipoTarjeta: "",
        };
    },
}
</script>
<style scoped>
    * {
        margin: 0;
    }
    body {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 60vh;
        font-size: 10px;
        font-family: sans-serif;
    }

    #app {
        display: flex;
        gap: 40px;
    }
    form {
        padding: 18px;
        border-radius: 20px;
        border: ridge 1px;
        box-shadow: 1px 1px 1px 1px gray;
        font-weight: bold;
        display: flex;
        flex-direction: column;
        gap: 15px;
        justify-content: center;
    }
    form div {
        display: grid;
        grid-template-columns: 100px 200px;
        align-items: center;
        gap: 5px;
    }

    form div label {
        text-align: right;
    }

    .carnet {
        width: 400px;
        height: 230px;
        background: #1c1a1e;
        color: white;
        border-radius: 20px;
        padding: 20px;
        box-shadow: 0px 0px 10px 2px black;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
    }

    h3 {
        font-size: 20px;
    }

    h2 {
        font-size: 30px;
        letter-spacing: 10px;
        margin-bottom: 15px;
        text-shadow: 0px 0px 1px gold;
        font-family: Times;
    }

    b {
        font-size: 16px;
    }
    #contenedorFecha{
        display: flex;
        flex-direction: row;
    }
    .fecha{
        width: 25px;
    }

    footer {
        display: flex;
        justify-content: space-between;
        align-items: flex-end;
        font-weight: bold;
        font-size: 18px;
        text-transform: uppercase;
        font-style: italic;
    }
</style>