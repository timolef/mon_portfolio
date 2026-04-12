<template>
  <nav :class="['fixed top-0 inset-x-0 z-50 transition-all duration-500', scrolled ? 'py-3' : 'py-5']">
    <!-- Backdrop -->
    <div
      :class="['absolute inset-0 transition-all duration-500', scrolled ? 'glass-dark shadow-xl shadow-black/30' : 'bg-transparent']">
    </div>

    <div class="relative max-w-7xl mx-auto px-6 flex items-center justify-between">
      <!-- Logo -->
      <a href="#hero" @click.prevent="scrollTo('hero')" class="group flex items-center gap-3">
        <div class="relative w-9 h-9 rounded-xl overflow-hidden">
          <div class="absolute inset-0 bg-gradient-to-br from-indigo-500 via-violet-500 to-purple-600 group-hover:scale-110 transition-transform duration-300"></div>
          <span class="relative z-10 flex items-center justify-center h-full text-white font-black text-sm font-mono">TL</span>
        </div>
        <span class="text-white/90 font-semibold text-sm hidden sm:block group-hover:text-white transition-colors">
          Timothée<span class="text-indigo-400">.</span>dev
        </span>
      </a>

      <!-- Desktop nav -->
      <div class="hidden md:flex items-center bg-white/[0.03] border border-white/[0.06] rounded-2xl px-2 py-1.5 gap-0.5">
        <a
          v-for="link in navLinks"
          :key="link.id"
          :href="`#${link.id}`"
          @click.prevent="scrollTo(link.id)"
          :class="[
            'px-4 py-2 rounded-xl text-sm font-medium transition-all duration-200',
            activeSection === link.id
              ? 'bg-indigo-500/15 text-indigo-300'
              : 'text-slate-500 hover:text-slate-200 hover:bg-white/[0.04]'
          ]"
        >{{ link.label }}</a>
      </div>

      <!-- Right actions -->
      <div class="flex items-center gap-2">
        <a
          href="https://www.linkedin.com/in/timothee-lefebvre/"
          target="_blank"
          class="hidden sm:flex w-9 h-9 items-center justify-center rounded-xl glass border border-white/[0.06] text-slate-500 hover:text-white hover:border-indigo-500/40 transition-all duration-200"
        >
          <Linkedin :size="15" />
        </a>
        <a
          href="#contact"
          @click.prevent="scrollTo('contact')"
          class="btn-primary py-2.5 px-5 text-xs"
        >
          Me contacter
        </a>
        <button @click="mobileOpen = !mobileOpen" class="md:hidden w-9 h-9 flex items-center justify-center rounded-xl glass border border-white/[0.06] text-slate-400">
          <Menu v-if="!mobileOpen" :size="18" />
          <X v-else :size="18" />
        </button>
      </div>
    </div>

    <!-- Mobile menu -->
    <Transition name="mobile-menu">
      <div v-if="mobileOpen" class="md:hidden relative glass-dark border-t border-white/[0.05] mt-2 px-6 py-5 flex flex-col gap-1">
        <a
          v-for="link in navLinks"
          :key="link.id"
          :href="`#${link.id}`"
          @click.prevent="scrollTo(link.id); mobileOpen = false"
          class="px-4 py-3 rounded-xl text-sm text-slate-300 hover:text-white hover:bg-white/[0.05] transition-all font-medium"
        >{{ link.label }}</a>
      </div>
    </Transition>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { Linkedin, Menu, X } from 'lucide-vue-next'

const scrolled = ref(false)
const mobileOpen = ref(false)
const activeSection = ref('hero')

const navLinks = [
  { id: 'about', label: 'À propos' },
  { id: 'skills', label: 'Skills' },
  { id: 'experience', label: 'Parcours' },
  { id: 'projects', label: 'Projets' },
  { id: 'contact', label: 'Contact' },
]

function scrollTo(id) {
  document.getElementById(id)?.scrollIntoView({ behavior: 'smooth' })
}

function onScroll() {
  scrolled.value = window.scrollY > 30
  const ids = ['hero', ...navLinks.map(l => l.id)]
  for (const id of [...ids].reverse()) {
    const el = document.getElementById(id)
    if (el && window.scrollY >= el.offsetTop - 140) { activeSection.value = id; break }
  }
}

onMounted(() => window.addEventListener('scroll', onScroll, { passive: true }))
onUnmounted(() => window.removeEventListener('scroll', onScroll))
</script>

<style scoped>
.mobile-menu-enter-active, .mobile-menu-leave-active { transition: all 0.2s ease; }
.mobile-menu-enter-from, .mobile-menu-leave-to { opacity: 0; transform: translateY(-6px); }
</style>
