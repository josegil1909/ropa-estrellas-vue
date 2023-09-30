<template >
  <main class=" border-4 border-gray-300 border-solid rounded p-4">

    <h1 class="text-3xl font-bold underline text-yellow-300">
      Estrellitas!
    </h1>
    <div>

      <Formulario v-for="(dataItem, index) in data" :key="index" :clave="index" :ropa="dataItem.ropa"
        :nota="dataItem.nota" :marca="dataItem.marca" @retorno="retorno" />
    </div>
  </main>
</template>

<script setup>
import Formulario from './components/Formulario.vue';
import { ref, computed } from 'vue';

const retorno = (a, i) => {
  if (a > 5) {
    return data.value[i].nota = 1;
  }
  data.value[i].nota = a;

}

const data = ref([
  {
    ropa: "camiseta",
    marca: "adidas",
    nota: 5,
  },
  {
    ropa: "pantalon",
    marca: "nike",
    nota: 4
  },
  {
    ropa: "zapatos",
    marca: "fila",
    nota: 3,
  }, {
    ropa: "gorra",
    marca: "puma",
    nota: 5
  }
  ,{
    ropa: "blusa",
    marca: "adidas",
    nota: 4
  }
]);

let id = ref(0);

const ropa = computed(() => {
  return data[id.value].ropa;
});

const marca = computed(() => {
  return data[id.value].marca
});

const nota = computed(() => {
  if (data[id.value].nota > 5) {
    return (data[id.value].nota = id.value);
  }
  return data[id.value].nota;
});

</script>

<style scoped></style>