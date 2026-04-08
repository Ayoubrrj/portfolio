<template>
    <section
        id="hero"
        class="min-h-screen flex items-center pt-32 pb-12 px-6 md:px-12 lg:px-24 max-w-screen-2xl mx-auto"
    >
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center w-full">
            <div class="flex flex-col gap-6 order-2 lg:order-1">
                <h1
                    class="text-5xl md:text-6xl lg:text-7xl text-brand-dark leading-tight"
                >
                    Hello ! Je m'appelle Ayoub.
                </h1>

                <p
                    class="text-lg md:text-xl text-brand-dark/80 max-w-2xl leading-relaxed"
                >
                    Je suis étudiant en développement web. Mon but actuel :
                    sortir des projets d'école et mettre les mains sur des vrais
                    cas concrets. J'ai l'énergie, la motivation, il ne me manque
                    plus qu'un environnement pro pour faire mes preuves.
                </p>

                <div class="flex items-center gap-6 mt-4">
                    <a
                        href="https://github.com/Ayoubrrj"
                        target="_blank"
                        class="flex items-center gap-2 hover:opacity-60 transition-opacity"
                    >
                        <Github class="w-6 h-6 stroke-1.5" />
                        <span class="font-medium">GitHub</span>
                    </a>
                    <a
                        href="#"
                        target="_blank"
                        class="flex items-center gap-2 hover:opacity-60 transition-opacity"
                    >
                        <FileText class="w-6 h-6 stroke-1.5" />
                        <span class="font-medium">Mon CV</span>
                    </a>
                </div>
            </div>

            <div class="flex justify-center lg:justify-end order-1 lg:order-2">
                <div
                    class="w-64 h-[400px] sm:w-80 sm:h-[500px] lg:w-[450px] lg:h-[650px] bg-brand-dark rounded-[50%] overflow-hidden relative shadow-2xl"
                >
                    <img
                        src="../../assets/images/self-portrait.png"
                        alt="Ayoub - Mes Passions"
                        class="w-full h-full object-cover"
                    />
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { Github, FileText } from "lucide-vue-next";
</script>
