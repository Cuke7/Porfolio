<template>
    <div class="flex flex-col sm:flex-row justify-start w-full my-16 sm:justify-center">
        <div :class="`flex flex-col sm:w-1/3 sm:justify-center sm:mx-40 ${app.leftAlign ? 'order-last' : ''}`">
            <div class="flex h-12 items-center">
                <div class="text-6xl text-white font-mono">
                    {{ app.name }}
                </div>
                <div v-if="app.app">
                    <img :src="app.iconUrl" v-if="app.name == 'Auditere' || 'Opal' || 'Aucellus'" class="ml-4 bg-black bg-opacity-50 rounded-full h-12 w-12" alt="" />
                    <img :src="app.iconUrl" v-else class="h-12 w-12 ml-4" alt="" />
                </div>
            </div>

            <div class="text-white text-lg mt-8" v-html="app.description"></div>

            <a :href="app.url" target="_blank" class="btn btn-ghost my-8 bg-orange-600 text-white font-bold mx-auto sm:mr-auto sm:ml-0">Essayer {{ app.name }}</a>
        </div>

        <div class="mockup-phone sm:w-1/5 mx-0" v-if="app.app">
            <div class="camera"></div>
            <div class="display">
                <img :src="app.name + '.jpg'" alt="" />
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import { Project } from "../types";
const props = defineProps<{
    app: Project;
}>();

const app = props.app;
</script>
