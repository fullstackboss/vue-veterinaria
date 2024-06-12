<script setup>
import { reactive } from 'vue'
const paciente = reactive({
    nombre: '',
    propietario: '',
    email: '',
    alta: '',
    sintomas: ''
})

const validar = () => {
    //console.log(Object.values(paciente));
    if (Object.values(paciente).includes('')) {
        console.log('estan vacios')
        return
    }

    console.log('agregando...');
}
</script>

<template>
    <div class="md:w-1/2">
        <h2 class="font-black text-3xl text-center">
            Seguimiento Pacientes
        </h2>
        <p class="text-lg mt-5 text-center mb-10">
            Añade pacientes y <span class="text-indigo-600 font-bold">Administralos</span>
        </p>
        <form class="bg-white shadow-xl rounded-lg py-6 px-5 mb-10" @submit.prevent="validar">

            <div class="mb-5">
                <label for="mascota" class="block text-gray-700 uppercase font-bold">
                    Nombre mascota - {{ paciente.nombre }}
                </label>
                <input type="text" id="mascota" class="border-2 w-full p-2 mt-2 placeholder-gray-300 rounded-md"
                    placeholder="Nombre de la mascota" v-model="paciente.nombre">
            </div>
            <div class="mb-5">
                <label for="propietario" class="block text-gray-700 uppercase font-bold">
                    Nombre propietario - {{ paciente.propietario }}
                </label>
                <input type="text" id="propietario" class="border-2 w-full p-2 mt-2 placeholder-gray-300 rounded-md"
                    placeholder="Nombre del Propietario" v-model="paciente.propietario">
            </div>
            <div class="mb-5">
                <label for="email" class="block text-gray-700 uppercase font-bold">
                    Email - {{ paciente.email }}
                </label>
                <input type="text" id="email" class="border-2 w-full p-2 mt-2 placeholder-gray-300 rounded-md"
                    placeholder="Email del Propietario" v-model="paciente.email">
            </div>
            <div class="mb-5">
                <label for="alta" class="block text-gray-700 uppercase font-bold">
                    Alta - {{ paciente.alta }}
                </label>
                <input type="date" id="alta" class="border-2 w-full p-2 mt-2 placeholder-gray-300 rounded-md"
                    v-model="paciente.alta">
            </div>

            <div class="mb-5">
                <label for="sintomas" class="block text-gray-700 uppercase font-bold">
                    Sintomas - {{ paciente.sintomas }}
                </label>
                <textarea id="sintomas" placeholder="Describir los sintomas"
                    class="border-2 w-full p-2 mt-2 placeholder-gray-300 rounded-md" v-model="paciente.sintomas">
                </textarea>
            </div>
            <input type="submit"
                class="bg-indigo-600 w-full p-3 text-white uppercase rounded-full font-bold hover:bg-indigo-800 cursor-pointer transition-colors">
            </input>
        </form>
    </div>
</template>
