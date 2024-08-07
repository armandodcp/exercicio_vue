<script setup>
const props = defineProps(['primeiroNumero', 'editaPrimeiroNumero', 'alteraOperacao', 'segundoNumero', 'editaSegundoNumero']);
</script>

<template>
    <div class="row mb-5 justify-content-center">
        <div class="col-md-2">
            <input :value="props.primeiroNumero" @change="props.editaPrimeiroNumero" class="form-control text-center"
                placeholder="Digite um número" type="number" />
        </div>
        <div class="col-md-1 t">
            <select @change="props.alteraOperacao" class="form-select text-center">
                <option value="adicao">+</option>
                <option value="subtracao">-</option>
                <option value="multiplicacao">*</option>
                <option value="divisao">/</option>
            </select>
        </div>
        <div class="col-md-2">
            <input :value="props.segundoNumero" @change="props.editaSegundoNumero" class="form-control text-center"
                placeholder="Digite outro número" type="number" />
        </div>
    </div>
</template>
