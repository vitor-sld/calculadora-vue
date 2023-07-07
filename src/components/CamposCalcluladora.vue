<script setup>

const props = defineProps(['funcCalcular', 'editarPrimeiroCampo', 'editarSegundoCampo', 'editarSelect'])
</script>

<template>

<div class="row px-3 text-center h2 d-flex justify-content-between pb-5 align-items-center">
                <div class="col-5">
                    <input type="number" placeholder="Digite um valor"
                        v-on:keyup="props.editarPrimeiroCampo" class="form-control">
                </div>
                <!-- "e => { estado.operador = e.target.value; pomps.funcCalcular }" -->
                <div class="col-1">
                    <select @change="props.editarSelect"
                        class="custom-select alinhamento bold">
                        <option selected value="adicao">+</option>
                        <option value="subtracao">-</option>
                        <option value="multiplicacao">*</option>
                        <option value="divisao">/</option>
                    </select>
                </div>

                <div class="col-5">
                    <input class="form-control" placeholder="Digite outro valor" type="number"
                        v-on:keyup="editarSegundoCampo">
                </div>
            </div>


</template>

<style scoped></style>