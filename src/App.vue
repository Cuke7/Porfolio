<template>
    <div id="app" class="p-8 bg-slate-800 flex flex-col">
        <a class="fixed top-8 left-8 text-lg text-white font-bold cursor-pointer underline" href="https://louiscassany.carrd.co">Photos</a>
        <div v-for="app in apps" class="w-full">
            <AppDemo :app="app" />
        </div>
    </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import AppDemo from "./components/AppDemo.vue";
import { Project } from "./types";

const apps = ref<Project[]>([
    {
        name: "Quotidie",
        description: "Reçois tous les jours à 9h l'évangile du jour ! Quotidie te donne aussi le saint du jour et un recueil de prières.",
        iconUrl: "icon_quotidie.png",
        url: "https://quotidie.fr",
        leftAlign: true,
        app: true,
    },
    {
        name: "Opal",
        description: "Application de prise de note en markdown avec synchronisation des notes en ligne.",
        iconUrl: "icon_opal.png",
        url: "https://opal-app.netlify.app",
        leftAlign: false,
        app: true,
    },
    {
        name: "Auditere",
        iconUrl: "icon_auditere.png",
        description: "Permet de rechercher et lire de la musique sur Youtube tout en vérouillant le téléphone. Peut aussi enregistrer et lire des playlists crées sur Youtube.",
        url: "https://auditere.vercel.app",
        leftAlign: true,
        app: true,
    },
    {
        name: "Aucellus",
        iconUrl: "icon_aucellus.png",
        description: "Informations, photos et cris d'oiseaux. Données issues du site oiseaux.net.",
        url: "https://birds-kappa.vercel.app",
        leftAlign: false,
        app: true,
    },
    {
        name: "Boids",
        iconUrl: "",
        description: "Simulation de vol d'un groupe d'oiseaux. Inspiré de <a class='underline' href='https://www.youtube.com/watch?v=bqtqltqcQhw' target='_blank'>https://www.youtube.com/watch?v=bqtqltqcQhw</a>. A consulter sur ordinateur pour conserver la mise en page.",
        url: "https://cuke7.github.io/Boids/",
        leftAlign: true,
        app: false,
    },
]);
</script>

<style>
#app {
    background-image: linear-gradient(to right top, #3a46c9, #0072e1, #008ed2, #00a3ad, #00b389);
}
</style>
