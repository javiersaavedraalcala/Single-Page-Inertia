<template>
    <app-layout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Modulo de Notas
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="md:grid md:grid-cols-3 md:gap-6">   
                    <div class="md:col-span-1">
                        <div class="px-4 sm:px-0">
                            <h3 class="text-lg text-gray-900">Listado de Notas</h3>
                            <p class="text-sm text-gray-600">Toma el registro correcto y ejecuta cualquer funcion (ver, editar, eliminar).</p>
                        </div>
                    </div>
                    <div class="md:col-span-2 mt-5 md:mt-0">
                        <div class="shadow bg-white md:rounded-md p-4">
                            <inertia-link :href="route('notes.create')" class="bg-blue-500 text-white font-bold px-4 py-2 rounded-md">
                                Crear
                            </inertia-link>
                            <table class="mt-3"> 
                                <tr v-for="item in notes" :key="item.id">
                                    <td class="border px-4 py-2"> 
                                        {{ item.excerpt }}
                                    </td>
                                    <td class="px-4 py-2"> 
                                        <inertia-link :href="route('notes.show', item.id)">
                                            Ver
                                        </inertia-link>
                                    </td>
                                    <td class="px-4 py-2"> 
                                        <inertia-link :href="route('notes.edit', item.id)">
                                            Editar
                                        </inertia-link>
                                    </td>
                                </tr>
                            </table>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </app-layout>
</template>

<script>
    import AppLayout from '@/Layouts/AppLayout'
    import Welcome from '@/Jetstream/Welcome'

    export default {
        components: {
            AppLayout,
            Welcome,
        },
        props: {
            notes: Array,
        }
    }
</script>
