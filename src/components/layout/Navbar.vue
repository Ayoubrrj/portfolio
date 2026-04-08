<template>
    <header
        class="fixed top-0 left-0 w-full z-50 py-6 md:py-8 pointer-events-none"
    >
        <div
            class="container mx-auto px-4 flex justify-center pointer-events-auto"
        >
            <nav
                class="flex items-center justify-between w-full max-w-[320px] md:max-w-[500px] px-10 md:px-14 py-3 md:py-4 bg-white/10 backdrop-blur-lg border border-white/20 rounded-full shadow-[inset_0_2px_4px_rgba(255,255,255,0.1)] transition-all"
            >
                <a
                    href="#hero"
                    class="text-brand-dark opacity-70 hover:opacity-100 transition-opacity"
                >
                    <Home class="w-5 h-5 md:w-6 md:h-6" />
                </a>
                <a
                    href="#projects"
                    class="text-brand-dark opacity-70 hover:opacity-100 transition-opacity"
                >
                    <Code class="w-5 h-5 md:w-6 md:h-6" />
                </a>
                <a
                    href="#about"
                    class="text-brand-dark opacity-70 hover:opacity-100 transition-opacity"
                >
                    <User class="w-5 h-5 md:w-6 md:h-6" />
                </a>
                <a
                    href="#contact"
                    class="text-brand-dark opacity-70 hover:opacity-100 transition-opacity"
                >
                    <Mail class="w-5 h-5 md:w-6 md:h-6" />
                </a>
            </nav>
        </div>
    </header>
</template>

<script setup>
import { Home, Code, User, Mail } from "lucide-vue-next";
</script>
