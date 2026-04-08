<template>
    <div class="font-sans antialiased text-brand-dark bg-brand-light">
        <Navbar />

        <main>
            <HeroSection />
            <ProjectsSection />
            <AboutSection />
            <ContactSection />
        </main>

        <Footer />
    </div>
</template>

<script setup>
// Imports des composants de structure
import Navbar from "./components/layout/Navbar.vue";
import Footer from "./components/layout/Footer.vue";

// Imports des sections de la page
import HeroSection from "./components/sections/HeroSection.vue";
import ProjectsSection from "./components/sections/ProjectsSection.vue";
import AboutSection from "./components/sections/AboutSection.vue";
import ContactSection from "./components/sections/ContactSection.vue";
</script>

<style></style>
