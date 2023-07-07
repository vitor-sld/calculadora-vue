<script setup>

    const props = defineProps(['resultadoCampo'])
</script>

<template>
      <div class="row px-3 text-light text-center h2 d-flex justify-content-center  ">
                    <div class="col-5">
                        <h2 class="h3 ">Resultado:</h2>
                    </div>
                </div>
    <div class="row px-3 text-center h2 d-flex justify-content-center mb-4">
        <div class="col-5 text-light h1">
            {{ props.resultadoCampo }}
        </div>
    </div>
</template>

<style scoped></style>