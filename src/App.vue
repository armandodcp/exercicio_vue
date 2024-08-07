<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Formulario from './components/Formulario.vue';
import Resultado from './components/Resultado.vue';

const estado = reactive({
  primeiroNumero: 0,
  segundoNumero: 0,
  operacao: 'adicao',
});

const calculaResultado = () => {
  const { operacao, primeiroNumero, segundoNumero } = estado;

  switch (operacao) {
    case 'adicao':
      return primeiroNumero + segundoNumero;
    case 'subtracao':
      return primeiroNumero - segundoNumero;
    case 'multiplicacao':
      return primeiroNumero * segundoNumero;
    case 'divisao':
      return segundoNumero !== 0 ? primeiroNumero / segundoNumero : '[ Erro ] divisão por zero';
    default:
      return 0;
  }
};
</script>

<template>
  <div class="container mt-5 p-5">
    <Cabecalho />
    <Formulario :primeiro-numero="estado.primeiroNumero"
      :edita-primeiro-numero="evento => estado.primeiroNumero = +evento.target.value"
      :altera-operacao="evento => estado.operacao = evento.target.value" :segundo-numero="estado.segundoNumero"
      :edita-segundo-numero="evento => estado.segundoNumero = +evento.target.value" />
    <Resultado :calcula-resultado="calculaResultado()" />
  </div>
</template>

<style scoped>
.container {
  border: 1px solid #dddddd;
  border-radius: 8px;
}
</style>
