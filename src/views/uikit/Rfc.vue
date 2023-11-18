<script setup>
import { ref } from 'vue';

const dropdownItems = ref([
    { name: 'Option 1', code: 'Option 1' },
    { name: 'Option 2', code: 'Option 2' },
    { name: 'Option 3', code: 'Option 3' }
]);

const dropdownItem = ref(null);
</script>

<template>
    <div class="grid">
        <div class="col-12 md:col-12">
            <div class="card p-fluid">
                <h5>Ingresa tus datos</h5>
                <div class="field">
                    <label for="name">Nombre (s):</label>
                    <InputText id="name" type="text" />
                </div>
                <div class="field">
                    <label for="Apaterno">Apellido Paterno</label>
                    <InputText id="Apaterno" type="text" />
                </div>
                <div class="field">
                    <label for="Amaterno">Apellido Materno</label>
                    <InputText id="Amaterno" type="text" />
                </div>
                <div class="field">
                    <label for="Fecha">Fecha de Nacimiento</label>
                    <InputText id="Fecha" type="text" />
                </div>
                <div class="field">
                    <label for="rfc1">RFC</label>
                    <InputText id="rfc1" type="text" />
                </div>
                <div>
                    <button type="button" class="btn btn-primary btn-lg">Generar RFC</button>
                </div>
            </div>

            
        </div>

           </div>
</template>
