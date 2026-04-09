<template>
    <section
        id="projects"
        class="min-h-screen bg-brand-beige flex items-center py-24"
    >
        <div
            class="container mx-auto px-6 md:px-12 grid grid-cols-1 lg:grid-cols-2 h-full gap-12"
        >
            <div class="flex flex-col justify-center">
                <h2
                    class="text-5xl font-serif text-brand-dark mb-8 border-b border-brand-dark/30 pb-4"
                >
                    Mes Projets
                </h2>

                <div class="flex flex-col">
                    <div
                        v-for="(project, index) in projects"
                        :key="index"
                        @mouseenter="activeProject = index"
                        class="group flex justify-between items-center py-8 border-b border-brand-dark/30 transition-colors"
                    >
                        <a
                            :href="project.github"
                            target="_blank"
                            rel="noopener noreferrer"
                            class="text-4xl font-serif text-brand-dark group-hover:pl-4 hover:text-brand-dark/70 transition-all duration-300"
                            title="Voir sur GitHub"
                        >
                            {{ project.title }}
                        </a>

                        <p
                            class="text-sm font-sans text-brand-dark/70 whitespace-pre-line text-right transition-all duration-300 group-hover:font-bold group-hover:text-brand-dark"
                        >
                            {{ project.tech }}
                        </p>
                    </div>
                </div>
            </div>

            <div class="hidden lg:flex items-center justify-center w-full">
                <div
                    class="w-full max-w-[500px] xl:max-w-[800px] h-[80vh] bg-brand-dark relative overflow-hidden transition-all duration-500"
                >
                    <img
                        v-if="
                            activeProject !== null &&
                            projects[activeProject].image
                        "
                        :src="projects[activeProject].image"
                        :alt="projects[activeProject].title"
                        class="absolute inset-0 w-full h-full object-cover animate-fade-in"
                    />
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref } from "vue";

import githubProfilImg from "../../assets/images/github-profil.png";
import ShoppingCardImg from "../../assets/images/ShoppingCard.png";
import buildAndRespawnImg from "../../assets/images/build-and-respawn.png";
import autreImg from "../../assets/images/autre.png";

// On commence à 0 (le premier projet)
const activeProject = ref(0);

const projects = [
    {
        title: "Shopping card",
        tech: "Html\nTailwind Css\nVue.js",
        image: ShoppingCardImg,
        github: "https://examen-framewwork-client.vercel.app/",
    },
    {
        title: "Build and Respawn",
        tech: "Wordpress\ntheme\nplugin",
        image: buildAndRespawnImg,
    },
    {
        title: "Projets Perso",
        tech: "Html\nCss\nJs",
        image: autreImg,
    },
    {
        title: "Autres Projets",
        tech: "Vue.js\nPhp/Laravel\nSql",
        image: githubProfilImg,
        github: "https://github.com/Ayoubrrj",
    },
];
</script>

<style scoped>
.animate-fade-in {
    animation: fadeIn 0.4s ease-in-out forwards;
}
@keyframes fadeIn {
    from {
        opacity: 0;
    }
    to {
        opacity: 1;
    }
}
</style>
