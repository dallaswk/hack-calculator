<script setup lang="ts">
import { computed, ref } from 'vue';

const valorInicial = ref<number>(0);
const desviacion = ref<number>(0);

const calcularPositivo = computed(() => valorInicial.value / (1 + desviacion.value / 100));
const calcularNegativo = computed(() => valorInicial.value / (1 - desviacion.value / 100));
</script>



<template>
  <div class="zero-wrapper">
    <div class="max-w-md p-6 mx-auto space-y-6 bg-gray-200 border-4 border-yellow-500 shadow-lg rounded-xl">
      <h2 class="text-2xl font-extrabold tracking-widest text-center text-orange-400">Frequency Hack Calculator</h2>
      <div>
        <label class="block text-sm font-medium text-gray-200">Valor Inicial</label>
        <input type="number" v-model.number="valorInicial"
          class="w-full p-4 mt-2 text-white transition-all duration-300 bg-gray-800 border-2 border-gray-700 rounded-md focus:ring-2 focus:ring-yellow-500 focus:outline-none hover:border-yellow-400" />
      </div>
      <div>
        <label class="block text-sm font-medium text-gray-200">% Desviación</label>
        <input type="number" v-model.number="desviacion"
          class="w-full p-4 mt-2 text-white transition-all duration-300 bg-gray-800 border-2 border-gray-700 rounded-md focus:ring-2 focus:ring-yellow-500 focus:outline-none hover:border-yellow-400" />
      </div>
      <div class="p-4 space-y-2 bg-gray-800 border-2 border-yellow-500 rounded-md">
        <p class="font-mono text-lg text-gray-200"><strong>Desviación Positiva:</strong> <span
            class="font-semibold text-yellow-400">{{ calcularPositivo.toFixed(0) }}</span></p>
        <p class="font-mono text-lg text-gray-200"><strong>Desviación Negativa:</strong> <span
            class="font-semibold text-red-400">{{ calcularNegativo.toFixed(0) }}</span></p>
      </div>
    </div>
    <span class="py-4 text-xs text-gray-600">Made with <span class="text-red-500">♥</span> by <strong class="text-blue-600">DallasWK</strong></span>
  </div>
</template>

<style scoped>
.font-mono {
  font-family: 'Courier New', monospace;
  letter-spacing: 1px;
}

.text-shadow {
  text-shadow: 0px 4px 6px rgba(255, 255, 0, 0.4), 0px 1px 3px rgba(255, 255, 0, 0.3);
}

.transform:hover {
  transform: scale(1.05) rotate(1deg);
}
</style>
