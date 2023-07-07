<script setup>

import { reactive } from "vue";
import Cabecalho from './components/Cabecalho.vue'
import Campos from './components/CamposCalcluladora.vue';
import Resultado from './components/Resultado.vue';

const estado = reactive(
    {
        operador: "adicao",
        valor1: 0,
        valor2: 0,
        resultado: 0
    }
)

function calcula() {
    switch (estado.operador) {
        case 'adicao':
            estado.resultado = parseInt(estado.valor1) + parseInt(estado.valor2);
            break;

        case 'subtracao':
            estado.resultado = parseInt(estado.valor1) - parseInt(estado.valor2);
            break;

        case 'divisao':
            estado.resultado = parseInt(estado.valor1) / parseInt(estado.valor2);
            break;

        case 'multiplicacao':
            estado.resultado = parseInt(estado.valor1) * parseInt(estado.valor2);
            break;
    }
}


</script>

<template>
    <main class="main">

        <div class="container my-4 bg-primary py-3 px-4 rounded">
            
            <Cabecalho></Cabecalho>
            
            <section>              
                <Resultado :resultado-campo="estado.resultado"></Resultado>

                <!-- campos -->
                <Campos :func-calcular="calcula()"
                    :editar-primeiro-campo="e => { estado.valor1 = e.target.value; calcula() }"
                    :editar-segundo-campo="e => { estado.valor2 = e.target.value; calcula() }"
                    :editarSelect="e => { estado.operador = e.target.value; calcula() }"> </Campos>

            </section>
        </div>

    </main>
</template>

<style scoped>
input[type=number]::-webkit-inner-spin-button {
    -webkit-appearance: none;

}

input[type=number] {
    -moz-appearance: textfield;
    appearance: textfield;
}


.main {
    height: 100vh;
    width: 100vw;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>
