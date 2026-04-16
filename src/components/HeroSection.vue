<template>
  <section id="hero" class="relative min-h-screen flex flex-col items-center justify-center overflow-hidden noise">
    <!-- Background -->
    <div class="absolute inset-0 bg-[#02040a]"></div>
    <div class="absolute inset-0 dot-bg opacity-50"></div>

    <!-- Ambient orbs -->
    <div class="orb w-[700px] h-[700px] bg-indigo-600/[0.07] top-[-200px] left-[-200px]"></div>
    <div class="orb w-[500px] h-[500px] bg-violet-600/[0.06] bottom-[-150px] right-[-100px]"></div>
    <div class="orb w-[400px] h-[400px] bg-sky-500/[0.04] top-[40%] left-[50%] -translate-x-1/2"></div>

    <!-- Spinning rings -->
    <div class="absolute w-[850px] h-[850px] top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 rounded-full border border-white/[0.02] animate-spin-slow pointer-events-none"></div>
    <div class="absolute w-[650px] h-[650px] top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 rounded-full border border-white/[0.03] animate-spin-slow pointer-events-none" style="animation-direction:reverse;animation-duration:28s"></div>

    <!-- Content -->
    <div class="relative z-10 w-full max-w-7xl mx-auto px-6 pt-28 pb-20">
      <div class="grid lg:grid-cols-[1fr_480px] gap-16 xl:gap-24 items-center">

        <!-- Left: text -->
        <div>
          <!-- Status badge -->
          <div
            v-motion
            :initial="{ opacity:0, y:16 }"
            :enter="{ opacity:1, y:0, transition:{ delay:150, duration:600 } }"
            class="inline-flex items-center gap-2.5 px-4 py-2 glass border border-white/[0.07] rounded-2xl text-sm mb-10"
          >
            <span class="relative flex h-2 w-2">
              <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-400 opacity-75"></span>
              <span class="relative rounded-full h-2 w-2 bg-emerald-500"></span>
            </span>
            <span class="text-slate-400">Disponible · Erquinghem-Lys, France</span>
          </div>

          <!-- Heading -->
          <div
            v-motion
            :initial="{ opacity:0, y:24 }"
            :enter="{ opacity:1, y:0, transition:{ delay:250, duration:700 } }"
          >
            <h1 class="display-xl text-white mb-3 leading-none">
              Timothée<br>
              <span class="grad-blue">Lefebvre</span>
            </h1>
            <div class="flex items-center gap-3 mt-5 mb-8">
              <div class="h-px w-12 bg-gradient-to-r from-indigo-500 to-transparent"></div>
              <p class="text-slate-400 text-lg font-medium tracking-wide">
                Développeur <span class="text-white font-semibold">Fullstack</span> · Vue.js & Node.js
              </p>
            </div>
          </div>

          <!-- Description -->
          <div
            v-motion
            :initial="{ opacity:0, y:16 }"
            :enter="{ opacity:1, y:0, transition:{ delay:400, duration:600 } }"
            class="text-slate-400 text-xl leading-relaxed max-w-xl mb-12"
          >
            Je conçois des applications web <span class="text-slate-200 font-medium">modernes et performantes</span>
            — du design API au rendu UI — avec une obsession pour la qualité et l'expérience utilisateur.
          </div>

          <!-- CTAs -->
          <div
            v-motion
            :initial="{ opacity:0, y:16 }"
            :enter="{ opacity:1, y:0, transition:{ delay:550, duration:600 } }"
            class="flex flex-wrap gap-3 mb-16"
          >
            <a href="#projects" @click.prevent="scrollTo('projects')" class="btn-primary">
              <Layers :size="17" />
              <span>Voir mes projets</span>
              <ArrowRight :size="15" />
            </a>
            <a href="#contact" @click.prevent="scrollTo('contact')" class="btn-ghost">
              <Mail :size="17" />
              <span>Me contacter</span>
            </a>
            <a href="/cv-timothee-lefebvre.pdf" download class="btn-ghost">
              <Download :size="17" />
              <span>CV</span>
            </a>
          </div>

          <!-- Stats row -->
          <div
            v-motion
            :initial="{ opacity:0 }"
            :enter="{ opacity:1, transition:{ delay:700 } }"
            class="flex flex-wrap gap-x-10 gap-y-4 border-t border-white/[0.05] pt-10"
          >
            <div v-for="s in stats" :key="s.label">
              <div class="text-3xl font-black text-white mb-0.5">{{ s.value }}</div>
              <div class="text-slate-500 text-xs font-medium uppercase tracking-wider">{{ s.label }}</div>
            </div>
          </div>
        </div>

        <!-- Right: Stack Architecture Visual -->
        <div
          v-motion
          :initial="{ opacity:0, scale:0.92 }"
          :enter="{ opacity:1, scale:1, transition:{ delay:400, duration:900, ease:'easeOut' } }"
          class="hidden lg:flex items-center justify-center"
        >
          <div class="relative w-full max-w-[460px] aspect-square">
            <!-- Glow behind -->
            <div class="absolute inset-0 bg-indigo-500/[0.06] rounded-full blur-3xl scale-75"></div>

            <!-- Central hub -->
            <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-28 h-28 rounded-3xl bg-gradient-to-br from-indigo-600 to-violet-600 flex flex-col items-center justify-center shadow-2xl shadow-indigo-500/30 z-20">
              <span class="text-white font-black text-xl font-mono">&lt;/&gt;</span>
              <span class="text-indigo-200 text-[9px] font-bold tracking-wider mt-1">FULLSTACK</span>
            </div>

            <!-- Orbital nodes -->
            <div
              v-for="(node, i) in orbitalNodes"
              :key="node.label"
              class="absolute z-10"
              :style="getNodePos(i, orbitalNodes.length, 170)"
            >
              <div
                class="card px-4 py-3 flex items-center gap-2.5 hover:!border-indigo-500/40 hover:!bg-white/[0.05] cursor-default transition-all duration-300"
                :class="node.float"
              >
                <span class="text-lg">{{ node.icon }}</span>
                <div>
                  <div class="text-white text-xs font-bold leading-none">{{ node.label }}</div>
                  <div class="text-slate-500 text-[10px] mt-0.5">{{ node.sub }}</div>
                </div>
              </div>
            </div>

            <!-- Connection lines (SVG) -->
            <svg class="absolute inset-0 w-full h-full z-0 pointer-events-none" viewBox="0 0 460 460">
              <line
                v-for="i in orbitalNodes.length"
                :key="i"
                :x1="230" :y1="230"
                :x2="getLinePosX(i - 1, orbitalNodes.length, 170)"
                :y2="getLinePosY(i - 1, orbitalNodes.length, 170)"
                stroke="url(#lineGrad)"
                stroke-width="1"
                stroke-dasharray="4 4"
                opacity="0.3"
              />
              <defs>
                <linearGradient id="lineGrad" x1="0" y1="0" x2="1" y2="1">
                  <stop stop-color="#6366f1" stop-opacity="0.5"/>
                  <stop offset="1" stop-color="#8b5cf6" stop-opacity="0.1"/>
                </linearGradient>
              </defs>
            </svg>
          </div>
        </div>
      </div>
    </div>

    <!-- Scroll cue -->
    <div class="absolute bottom-10 left-1/2 -translate-x-1/2 flex flex-col items-center gap-3 text-slate-700">
      <div class="w-[1px] h-16 bg-gradient-to-b from-transparent via-slate-600 to-transparent animate-pulse-soft"></div>
      <ChevronDown :size="14" class="animate-bounce" />
    </div>
  </section>
</template>

<script setup>
import { Layers, Mail, Download, ArrowRight, ChevronDown } from 'lucide-vue-next'

const stats = [
  { value: '4+', label: 'Ans d\'expérience' },
  { value: '3+', label: 'Projets livrés' },
  { value: '5+', label: 'Clients' },
  { value: '2025', label: 'Master Supinfo' },
]

const orbitalNodes = [
  { icon: '💚', label: 'Vue.js', sub: 'Frontend', float: 'animate-float' },
  { icon: '⚛️', label: 'React', sub: 'Frontend', float: 'animate-float2' },
  { icon: '🟢', label: 'Node.js', sub: 'Backend', float: 'animate-float' },
  { icon: '🐳', label: 'Docker', sub: 'DevOps', float: 'animate-float2' },
  { icon: '🗄️', label: 'SQL', sub: 'Database', float: 'animate-float' },
  { icon: '🔄', label: 'CI/CD', sub: 'Pipeline', float: 'animate-float2' },
]

function getNodePos(i, total, radius) {
  const angle = (i / total) * 2 * Math.PI - Math.PI / 2
  const x = Math.cos(angle) * radius + 230
  const y = Math.sin(angle) * radius + 230
  return {
    left: `${x - 50}px`,
    top: `${y - 22}px`,
  }
}

function getLinePosX(i, total, radius) {
  const angle = (i / total) * 2 * Math.PI - Math.PI / 2
  return Math.cos(angle) * radius + 230
}

function getLinePosY(i, total, radius) {
  const angle = (i / total) * 2 * Math.PI - Math.PI / 2
  return Math.sin(angle) * radius + 230
}

function scrollTo(id) {
  document.getElementById(id)?.scrollIntoView({ behavior: 'smooth' })
}
</script>
