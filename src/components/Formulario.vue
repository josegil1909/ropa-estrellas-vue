<template >
    <div class="bg-gray text-black rounded">

        <form action="retorno" @submit.prevent>
            <div class="flex flex-row space-x-5 text-xl mt-5 ">
                <div class="basis-1/2 bg-red-500 rounded py-2 px-4 text-center"
                    style="background-color: rgb(184, 184, 184); ">
                    <span class="font-bold" for="ropa">({{ ropa }}) </span>
                    <span class="" for="ropa"> &nbsp;{{ marca }}</span>

                </div>
                <div class=" grid grid-cols-5   bg-blue-500 rounded py-2 px-4 text-center">
                    <!-- <label for="ropa">Estrellas</label> -->
                    <img v-for="(notas, index) in nota" src="/estrellita.png" height="50" width="30">

                </div>
                <button @click="incrementarNota(nota, clave)" class="basis-1/10 bg-slate-500 rounded py-2 px-4 text-center"
                    type="submit">+</button>
            </div>

        </form>
    </div>
</template>


<script setup>
import { ref, computed } from 'vue';



const emit = defineEmits(['retorno']);

const incrementarNota = (a, i) => {
    a++;

    emit('retorno', a, i);
}

const props = defineProps({
    marca: String,
    ropa: String,
    nota: Number,
    clave: Number,

})






</script>


<style scoped></style>