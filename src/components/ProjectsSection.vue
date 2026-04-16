<template>
  <section id="projects" class="relative py-36 overflow-hidden noise">
    <div class="absolute inset-0 bg-[#02040a]"></div>
    <div class="orb w-[600px] h-[600px] bg-violet-700/[0.05] top-[-100px] right-[-200px]"></div>
    <div class="divider"></div>

    <div class="relative z-10 max-w-7xl mx-auto px-6">
      <!-- Header -->
      <div class="section-header reveal">
        <div class="section-badge">🛠️ Réalisations</div>
        <h2 class="display-lg text-white">
          Projets <span class="grad-blue">sélectionnés</span>
        </h2>
        <p class="text-slate-400 text-lg max-w-xl mx-auto mt-4">
          Des projets concrets qui illustrent ma capacité à livrer des produits complets, du design à la mise en production.
        </p>
      </div>

      <!-- Featured project -->
      <div class="reveal mb-10">
        <div class="card overflow-hidden group hover:!shadow-2xl hover:!shadow-indigo-500/10">
          <div class="grid lg:grid-cols-2 gap-0">
            <!-- Visual -->
            <div class="relative h-72 lg:h-auto min-h-[320px] overflow-hidden">
              <div class="absolute inset-0 bg-gradient-to-br from-[#0f172a] via-[#0e1630] to-[#1e1b4b]">
                <div class="absolute inset-0 dot-bg opacity-40"></div>
                <!-- Dashboard mockup -->
                <div class="absolute inset-6 flex items-center justify-center">
                  <svg viewBox="0 0 440 300" class="w-full max-w-[400px] drop-shadow-2xl" xmlns="http://www.w3.org/2000/svg">
                    <rect width="440" height="300" rx="14" fill="#0f172a" stroke="rgba(255,255,255,0.06)" stroke-width="1"/>
                    <!-- Top bar -->
                    <rect x="0" y="0" width="440" height="36" rx="14" fill="#131b2e"/>
                    <rect x="0" y="14" width="440" height="22" fill="#131b2e"/>
                    <circle cx="20" cy="18" r="4.5" fill="#ef4444" opacity="0.8"/>
                    <circle cx="34" cy="18" r="4.5" fill="#eab308" opacity="0.8"/>
                    <circle cx="48" cy="18" r="4.5" fill="#22c55e" opacity="0.8"/>
                    <rect x="160" y="13" width="120" height="10" rx="5" fill="rgba(255,255,255,0.04)"/>
                    <!-- Sidebar -->
                    <rect x="0" y="36" width="64" height="264" fill="#0a1120"/>
                    <rect x="14" y="52" width="36" height="6" rx="3" fill="rgba(99,102,241,0.3)"/>
                    <rect x="14" y="70" width="36" height="4" rx="2" fill="rgba(255,255,255,0.06)"/>
                    <rect x="14" y="82" width="36" height="4" rx="2" fill="rgba(255,255,255,0.06)"/>
                    <rect x="14" y="94" width="36" height="4" rx="2" fill="rgba(255,255,255,0.06)"/>
                    <rect x="8" y="110" width="48" height="22" rx="6" fill="rgba(99,102,241,0.15)"/>
                    <rect x="14" y="142" width="36" height="4" rx="2" fill="rgba(255,255,255,0.04)"/>
                    <rect x="14" y="154" width="36" height="4" rx="2" fill="rgba(255,255,255,0.04)"/>
                    <!-- Stats cards -->
                    <rect x="80" y="48" width="105" height="56" rx="10" fill="#131b2e"/>
                    <rect x="92" y="60" width="40" height="4" rx="2" fill="rgba(255,255,255,0.08)"/>
                    <rect x="92" y="78" width="56" height="14" rx="4" fill="rgba(99,102,241,0.2)"/>
                    <rect x="195" y="48" width="105" height="56" rx="10" fill="#131b2e"/>
                    <rect x="207" y="60" width="40" height="4" rx="2" fill="rgba(255,255,255,0.08)"/>
                    <rect x="207" y="78" width="56" height="14" rx="4" fill="rgba(139,92,246,0.2)"/>
                    <rect x="310" y="48" width="114" height="56" rx="10" fill="#131b2e"/>
                    <rect x="322" y="60" width="40" height="4" rx="2" fill="rgba(255,255,255,0.08)"/>
                    <rect x="322" y="78" width="56" height="14" rx="4" fill="rgba(16,185,129,0.2)"/>
                    <!-- Chart -->
                    <rect x="80" y="116" width="224" height="130" rx="10" fill="#131b2e"/>
                    <rect x="96" y="130" width="60" height="5" rx="2.5" fill="rgba(255,255,255,0.07)"/>
                    <path d="M 96 210 Q 120 190 145 195 Q 170 200 195 175 Q 220 150 245 165 Q 270 180 288 155" stroke="url(#cGrad)" stroke-width="2.5" fill="none" stroke-linecap="round"/>
                    <path d="M 96 210 Q 120 200 145 205 Q 170 210 195 195 Q 220 180 245 190 Q 270 200 288 185" stroke="rgba(139,92,246,0.5)" stroke-width="2" fill="none" stroke-linecap="round" stroke-dasharray="3 4"/>
                    <!-- Table -->
                    <rect x="316" y="116" width="108" height="130" rx="10" fill="#131b2e"/>
                    <rect x="326" y="130" width="50" height="5" rx="2.5" fill="rgba(255,255,255,0.07)"/>
                    <rect x="326" y="148" width="88" height="8" rx="3" fill="rgba(255,255,255,0.04)"/>
                    <rect x="326" y="164" width="88" height="8" rx="3" fill="rgba(255,255,255,0.03)"/>
                    <rect x="326" y="180" width="88" height="8" rx="3" fill="rgba(255,255,255,0.04)"/>
                    <rect x="326" y="196" width="88" height="8" rx="3" fill="rgba(255,255,255,0.03)"/>
                    <rect x="326" y="212" width="88" height="8" rx="3" fill="rgba(255,255,255,0.04)"/>
                    <!-- Bottom chart -->
                    <rect x="80" y="258" width="344" height="32" rx="8" fill="#131b2e"/>
                    <defs>
                      <linearGradient id="cGrad" x1="0" y1="0" x2="1" y2="0">
                        <stop stop-color="#6366f1"/><stop offset="1" stop-color="#3b82f6"/>
                      </linearGradient>
                    </defs>
                  </svg>
                </div>
              </div>
              <div class="absolute top-4 left-4 z-10">
                <span class="px-3 py-1.5 bg-indigo-600/90 text-white text-xs font-bold rounded-lg backdrop-blur-sm shadow-lg">★ Featured</span>
              </div>
            </div>

            <!-- Content -->
            <div class="p-8 lg:p-10 flex flex-col justify-center">
              <div class="flex flex-wrap gap-1.5 mb-5">
                <span v-for="t in featured.tags" :key="t" class="tag text-[11px]">{{ t }}</span>
              </div>
              <h3 class="text-white font-bold text-2xl mb-3 leading-snug">{{ featured.title }}</h3>
              <p class="text-slate-400 text-sm leading-relaxed mb-8">{{ featured.desc }}</p>
              <div class="flex gap-3">
                <a :href="featured.demo" class="btn-primary text-sm py-2.5 px-5">
                  <ExternalLink :size="15" /> <span>Démo live</span>
                </a>
                <a :href="featured.github" class="btn-ghost text-sm py-2.5 px-5">
                  <Github :size="15" /> <span>Code</span>
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Project grid -->
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-5">
        <div
          v-for="(p, i) in otherProjects"
          :key="p.title"
          class="reveal card overflow-hidden group"
          :style="{ transitionDelay: (i * 80) + 'ms' }"
        >
          <!-- Visual -->
          <div :class="['h-44 relative overflow-hidden flex items-center justify-center', p.bgClass]">
            <div class="text-6xl transition-transform duration-500 group-hover:scale-110 group-hover:rotate-3">{{ p.emoji }}</div>
            <div class="absolute inset-0 bg-gradient-to-t from-[#02040a] via-transparent to-transparent opacity-80"></div>
            <div class="absolute bottom-3 left-4 flex flex-wrap gap-1.5">
              <span v-for="t in p.tags.slice(0,3)" :key="t" class="px-2 py-0.5 bg-black/50 backdrop-blur-md text-white/80 text-[10px] font-semibold rounded-md">{{ t }}</span>
            </div>
          </div>

          <!-- Content -->
          <div class="p-6">
            <h3 class="text-white font-bold text-base mb-2 group-hover:text-indigo-300 transition-colors">{{ p.title }}</h3>
            <p class="text-slate-500 text-sm leading-relaxed mb-5 line-clamp-3">{{ p.desc }}</p>
            <div class="flex gap-2.5">
              <a :href="p.demo" class="flex-1 flex items-center justify-center gap-1.5 py-2.5 bg-indigo-600/80 hover:bg-indigo-600 text-white text-xs font-bold rounded-xl transition-all">
                <ExternalLink :size="13" /> Démo
              </a>
              <a :href="p.github" class="flex-1 flex items-center justify-center gap-1.5 py-2.5 glass border border-white/[0.06] text-slate-400 hover:text-white text-xs font-bold rounded-xl transition-all">
                <Github :size="13" /> Code
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ExternalLink, Github } from 'lucide-vue-next'

const featured = {
  title: 'Association 48 pour 100',
  desc: 'Développement complet d\'une plateforme moderne pour l\'association 48 pour 100. Interface intuitive, performance optimale et maintenance évolutive.',
  tags: ['Vue 3', 'Node.js', 'Vercel', 'Portfolio'],
  demo: 'https://association48pour100.vercel.app/',
  github: 'https://github.com/timolef/48_front_new',
}

const otherProjects = [
  {
    title: 'Job Tracker',
    desc: 'Application de suivi de candidatures (Job Tracker) pour organiser et optimiser sa recherche d\'emploi avec un dashboard analytique.',
    tags: ['Next.js', 'Dashboard', 'Vercel'],
    demo: 'https://job-tracker-ten-sooty.vercel.app/dashboard',
    github: 'https://github.com/timolef/JobTracker',
    emoji: '💼',
    bgClass: 'bg-gradient-to-br from-blue-950/80 to-indigo-950/60',
  },
  {
    title: 'Predict Tycoon',
    desc: 'Application interactive "Predict Tycoon" intégrant des mécaniques de prédiction et de gestion.',
    tags: ['Web App', 'Tycoon', 'Stratégie'],
    demo: 'https://predicttycoon.web.app/', github: '#',
    emoji: '📈',
    bgClass: 'bg-gradient-to-br from-blue-950/80 to-indigo-950/60',
  }
]
</script>

<style scoped>
.line-clamp-3 {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
</style>
