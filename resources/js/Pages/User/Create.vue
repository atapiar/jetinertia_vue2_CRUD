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

                        <form @submit.prevent="submit">
                            <label for="">Nombre:</label>
                            <input type="text" v-model="form.name">
                            <input-error :message="errors.name" />
                            <label for="">Email:</label>
                            <input type="text" v-model="form.email">
                            <input-error :message="errors.email" />
                            <label for="">Contraseña:</label>
                            <input type="password" v-model="form.password">
                            <input-error :message="errors.password" />

                            <button type="submit">Enviar</button>
                        </form>

                    </div>
                    <!-- Hola mundo -->
                </div>
            </div>
        </div>
    </app-layout>
</template>

<script>
    import { Inertia } from '@inertiajs/inertia'
    import AppLayout from '@/Layouts/AppLayout'
    import InputError from '@/Jetstream/InputError'

    export default {
        props: ["errors"],
        data(){
            return{
                form: {
                    name: "",
                    email: "paola@gmail.com",
                    password: "123456"
                }
            }
        },
        components: {
            AppLayout,
            InputError,
        },
        methods: {
            submit(){
                Inertia.post(route('user.store'), this.form);
            }
        }
    }
</script>