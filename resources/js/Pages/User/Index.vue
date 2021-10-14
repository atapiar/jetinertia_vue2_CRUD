<template>
    <app-layout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Users
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-xl sm:rounded-lg">
                    <div class="p-6 sm:px-20 bg-white border-b border-gray-200">

                        <inertia-link :href="route('user.create')">Crear Usuario</inertia-link>

                        <table class="table-auto w-full">
                            <thead>
                                <tr>
                                    <th class="p-3">Id</th>
                                    <th class="p-3">Nombre</th>
                                    <th class="p-3">Email</th>
                                    <th class="p-3">Acciones</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr v-for="u in users" :key="u.id">
                                    <td class="p-3 border">{{ u.id }}</td>
                                    <td class="p-3 border">{{ u.name }}</td>
                                    <td class="p-3 border">{{ u.email }}</td>
                                    <td class="p-3 border">Acciones</td>
                                </tr>
                            </tbody>
                        </table>

                    </div>
                    <!-- Hola mundo -->
                </div>
            </div>
        </div>
    </app-layout>
</template>

<script>
    import AppLayout from '@/Layouts/AppLayout'

    export default {
        props: ['users'],
        components: {
            AppLayout,

        },
    }
</script>