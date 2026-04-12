<template>
  <footer class="relative bg-[#02040a] border-t border-white/[0.04] pt-16 pb-8 px-6">
    <div class="max-w-7xl mx-auto">
      <!-- Top row -->
      <div class="flex flex-col md:flex-row items-center justify-between gap-10 mb-14">
        <!-- Logo + tagline -->
        <div class="flex items-center gap-4">
          <div class="w-10 h-10 rounded-xl bg-gradient-to-br from-indigo-600 to-violet-600 flex items-center justify-center text-white font-black text-sm font-mono shadow-lg">TL</div>
          <div>
            <p class="text-white font-bold text-base">Timothée Lefebvre</p>
            <p class="text-slate-600 text-xs font-medium">Développeur Fullstack · Vue.js & Node.js</p>
          </div>
        </div>

        <!-- Nav links -->
        <div class="flex flex-wrap justify-center gap-6">
          <a v-for="l in links" :key="l.id" :href="`#${l.id}`" @click.prevent="scrollTo(l.id)"
            class="text-slate-500 hover:text-slate-200 text-sm font-medium transition-colors duration-200">
            {{ l.label }}
          </a>
        </div>

        <!-- Social -->
        <div class="flex items-center gap-2.5">
          <a href="https://www.linkedin.com/in/timothee-lefebvre/" target="_blank"
            class="w-9 h-9 rounded-xl glass border border-white/[0.06] flex items-center justify-center text-slate-500 hover:text-indigo-400 hover:border-indigo-500/30 transition-all duration-200">
            <Linkedin :size="15" />
          </a>
          <a href="mailto:leftim59@hotmail.fr"
            class="w-9 h-9 rounded-xl glass border border-white/[0.06] flex items-center justify-center text-slate-500 hover:text-violet-400 hover:border-violet-500/30 transition-all duration-200">
            <Mail :size="15" />
          </a>
          <button @click="scrollTo('hero')"
            class="w-9 h-9 rounded-xl glass border border-white/[0.06] flex items-center justify-center text-slate-500 hover:text-white hover:border-white/[0.15] transition-all duration-200">
            <ArrowUp :size="15" />
          </button>
        </div>
      </div>

      <!-- Divider -->
      <div class="h-px bg-gradient-to-r from-transparent via-white/[0.04] to-transparent mb-8"></div>

      <!-- Bottom -->
      <div class="flex flex-col sm:flex-row items-center justify-between gap-4">
        <p class="text-slate-700 text-xs text-center sm:text-left">
          © {{ new Date().getFullYear() }} Timothée Lefebvre · Conçu avec Vue 3 + Vite + Tailwind
        </p>
        <div class="flex items-center gap-4">
          <span class="text-slate-700 text-xs">Fait avec</span>
          <span class="text-red-500/60 text-sm">❤️</span>
          <span class="text-slate-700 text-xs">en France</span>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
import { Linkedin, Mail, ArrowUp } from 'lucide-vue-next'

const links = [
  { id: 'about', label: 'À propos' },
  { id: 'skills', label: 'Skills' },
  { id: 'experience', label: 'Parcours' },
  { id: 'projects', label: 'Projets' },
  { id: 'contact', label: 'Contact' },
]

function scrollTo(id) {
  document.getElementById(id)?.scrollIntoView({ behavior: 'smooth' })
}
</script>
