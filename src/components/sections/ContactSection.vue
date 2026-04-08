<template>
    <section id="contact" class="bg-brand-neutral py-24 px-6 md:px-12 relative">
        <div class="max-w-3xl mx-auto text-center mb-12">
            <h2 class="text-4xl md:text-5xl text-brand-light mb-4">
                Contactez-moi
            </h2>
            <p
                class="text-brand-light/90 max-w-xl mx-auto text-base md:text-lg"
            >
                Vous recherchez un stagiaire motivé et sérieux ou souhaitez en
                savoir plus sur mon profil ? Envoyez-moi un message, je vous
                répondrai rapidement.
            </p>
        </div>

        <div
            class="bg-brand-light rounded-[2rem] p-8 md:p-12 max-w-3xl mx-auto shadow-2xl"
        >
            <form class="flex flex-col gap-6" @submit.prevent>
                <div class="flex flex-col gap-2">
                    <label for="nom" class="text-xl text-brand-dark font-serif"
                        >Nom</label
                    >
                    <input
                        type="text"
                        id="nom"
                        placeholder="Votre nom"
                        class="px-4 py-4 rounded-xl border border-gray-300 focus:outline-none focus:border-brand-dark focus:ring-1 focus:ring-brand-dark transition-all bg-white font-sans"
                    />
                </div>

                <div class="flex flex-col gap-2">
                    <label
                        for="email"
                        class="text-xl text-brand-dark font-serif"
                        >Email</label
                    >
                    <input
                        type="email"
                        id="email"
                        placeholder="Votre email"
                        class="px-4 py-4 rounded-xl border border-gray-300 focus:outline-none focus:border-brand-dark focus:ring-1 focus:ring-brand-dark transition-all bg-white font-sans"
                    />
                </div>

                <div class="flex flex-col gap-2">
                    <label
                        for="message"
                        class="text-xl text-brand-dark font-serif"
                        >Message</label
                    >
                    <textarea
                        id="message"
                        rows="6"
                        placeholder="Votre message"
                        class="px-4 py-4 rounded-xl border border-gray-300 focus:outline-none focus:border-brand-dark focus:ring-1 focus:ring-brand-dark transition-all bg-white font-sans resize-none"
                    ></textarea>
                </div>

                <button
                    type="submit"
                    class="mt-4 bg-brand-dark text-brand-light py-4 px-8 rounded-xl text-lg hover:opacity-90 transition-opacity w-full font-serif tracking-wide"
                >
                    Envoyez
                </button>
            </form>
        </div>
    </section>
</template>

<script setup>
// Pas besoin de logique complexe ici pour le moment, le @submit.prevent empêche la page de se recharger
</script>
