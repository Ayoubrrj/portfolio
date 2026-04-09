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
            <form
                ref="formRef"
                class="flex flex-col gap-6"
                @submit.prevent="sendEmail"
            >
                <div class="flex flex-col gap-2">
                    <label for="nom" class="text-xl text-brand-dark font-serif"
                        >Nom</label
                    >
                    <input
                        type="text"
                        id="nom"
                        name="user_name"
                        v-model="formData.name"
                        placeholder="Votre nom"
                        required
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
                        name="user_email"
                        v-model="formData.email"
                        placeholder="Votre email"
                        required
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
                        name="message"
                        rows="6"
                        v-model="formData.message"
                        placeholder="Votre message"
                        required
                        class="px-4 py-4 rounded-xl border border-gray-300 focus:outline-none focus:border-brand-dark focus:ring-1 focus:ring-brand-dark transition-all bg-white font-sans resize-none"
                    ></textarea>
                </div>

                <p
                    v-if="statusMessage"
                    :class="statusClass"
                    class="text-center font-medium"
                >
                    {{ statusMessage }}
                </p>

                <button
                    type="submit"
                    :disabled="isSending"
                    class="mt-4 bg-brand-dark text-brand-light py-4 px-8 rounded-xl text-lg transition-opacity w-full font-serif tracking-wide disabled:opacity-70 disabled:cursor-not-allowed hover:opacity-90"
                >
                    {{ isSending ? "Envoi en cours..." : "Envoyer" }}
                </button>
            </form>
        </div>
    </section>
</template>

<script setup>
import { ref } from "vue";
import emailjs from "@emailjs/browser";

// Référence vers le formulaire HTML pour qu'EmailJS puisse le lire
const formRef = ref(null);

const isSending = ref(false);
const statusMessage = ref("");
const statusClass = ref("");

const formData = ref({
    name: "",
    email: "",
    message: "",
});

// Fonction d'envoi
const sendEmail = () => {
    isSending.value = true;
    statusMessage.value = "";

    const SERVICE_ID = "service_ydpqf4q";
    const TEMPLATE_ID = "template_pep7gzj";
    const PUBLIC_KEY = "ICiM5qMuZ-ORHLtMr";

    emailjs
        .sendForm(SERVICE_ID, TEMPLATE_ID, formRef.value, PUBLIC_KEY)
        .then(() => {
            // Succès
            statusMessage.value = "Merci ! Votre message a bien été envoyé.";
            statusClass.value = "text-green-600";

            // Vider le formulaire
            formData.value = { name: "", email: "", message: "" };
        })
        .catch((error) => {
            // Erreur
            console.error("Erreur EmailJS:", error);
            statusMessage.value =
                "Oups... Une erreur est survenue. Veuillez réessayer.";
            statusClass.value = "text-red-600";
        })
        .finally(() => {
            isSending.value = false;

            // Faire disparaître le message de succès après 5 secondes
            setTimeout(() => {
                statusMessage.value = "";
            }, 5000);
        });
};
</script>
