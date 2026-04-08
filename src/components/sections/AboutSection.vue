<template>
    <section
        id="about"
        class="min-h-screen bg-brand-light flex items-center justify-center py-24 px-6 relative overflow-hidden"
    >
        <div
            @mouseenter="isHovered = true"
            @mouseleave="isHovered = false"
            class="bg-brand-dark flex flex-col items-center justify-center cursor-pointer animate-blob transition-all duration-700 ease-[cubic-bezier(0.25,1,0.5,1)] will-change-[width,height,border-radius]"
            :class="
                isHovered
                    ? 'w-[85vw] h-[85vw] sm:w-[500px] sm:h-[500px] md:w-[650px] md:h-[650px]'
                    : 'w-[300px] h-[300px] md:w-[400px] md:h-[400px]'
            "
        >
            <h2
                v-show="!isHovered"
                class="text-4xl md:text-5xl font-serif text-brand-light transition-opacity duration-300 pointer-events-none text-center px-4"
            >
                À propos de moi
            </h2>

            <div
                v-show="isHovered"
                class="text-brand-light p-8 md:p-16 text-center animate-fade-in-delayed flex flex-col items-center justify-center w-full h-full pointer-events-none"
            >
                <h3
                    class="text-3xl md:text-4xl font-serif mb-4 border-b border-brand-light/30 pb-2 inline-block"
                >
                    Mon Parcours
                </h3>
                <p
                    class="font-sans text-sm sm:text-base md:text-lg leading-relaxed text-brand-light/90 max-w-md mx-auto"
                >
                    Passionné par le développement web, j'ai commencé mon
                    parcours en apprenant les bases du HTML, CSS et JavaScript.
                    Aujourd'hui, j'explore des technologies modernes comme
                    Vue.js et Tailwind pour créer des interfaces fluides et
                    esthétiques. J'aime résoudre des problèmes complexes et
                    donner vie à des designs créatifs.
                </p>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref } from "vue";

// État réactif pour savoir si la souris survole le blob
const isHovered = ref(false);
</script>

<style scoped>
/* Petit fade-in pour le texte intérieur quand il apparaît */
.animate-fade-in-delayed {
    animation: fadeInDelayed 0.8s ease-in-out forwards;
}

@keyframes fadeInDelayed {
    0% {
        opacity: 0;
        transform: translateY(15px);
    }
    40% {
        opacity: 0;
    } /* On attend un peu que le blob grandisse avant d'afficher le texte */
    100% {
        opacity: 1;
        transform: translateY(0);
    }
}
</style>
