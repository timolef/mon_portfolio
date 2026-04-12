<template>
  <section id="about" class="relative py-36 overflow-hidden noise">
    <div class="absolute inset-0 bg-[#030610]"></div>
    <div class="orb w-[500px] h-[500px] bg-indigo-700/6 top-0 right-[-150px]"></div>

    <div class="relative z-10 max-w-7xl mx-auto px-6">
      <!-- Header -->
      <div class="section-header reveal">
        <div class="section-badge">
          <span>👋</span> À propos de moi
        </div>
        <h2 class="display-lg text-white">
          Façonner le web,<br>
          <span class="grad-blue">pixel par pixel</span>
        </h2>
      </div>

      <div class="grid lg:grid-cols-2 gap-20 items-center">
        <!-- Avatar column -->
        <div class="reveal-left flex flex-col items-center gap-8">
          <!-- Avatar card -->
          <div class="relative">
            <div class="absolute -inset-6 rounded-[40px] border border-white/[0.04] animate-spin-slow"></div>
            <div class="relative w-64 h-64 md:w-80 md:h-80 rounded-3xl overflow-hidden border border-white/[0.07] shadow-2xl shadow-black/50">
              <svg viewBox="0 0 320 320" class="w-full h-full" xmlns="http://www.w3.org/2000/svg">
                <defs>
                  <linearGradient id="bg2" x1="0" y1="0" x2="1" y2="1">
                    <stop stop-color="#0d1117"/>
                    <stop offset="1" stop-color="#161b27"/>
                  </linearGradient>
                  <linearGradient id="shirt" x1="0" y1="0" x2="0" y2="1">
                    <stop stop-color="#312e81"/>
                    <stop offset="1" stop-color="#4c1d95"/>
                  </linearGradient>
                  <radialGradient id="face" cx="50%" cy="50%" r="60%">
                    <stop stop-color="#fde8c8"/>
                    <stop offset="1" stop-color="#f5c17c"/>
                  </radialGradient>
                  <radialGradient id="glow" cx="50%" cy="40%" r="60%">
                    <stop stop-color="rgba(99,102,241,0.15)"/>
                    <stop offset="1" stop-color="transparent"/>
                  </radialGradient>
                </defs>
                <rect width="320" height="320" fill="url(#bg2)"/>
                <!-- Grid -->
                <pattern id="g2" width="24" height="24" patternUnits="userSpaceOnUse">
                  <path d="M24 0L0 0 0 24" fill="none" stroke="rgba(255,255,255,0.025)" stroke-width="0.8"/>
                </pattern>
                <rect fill="url(#g2)" width="320" height="320"/>
                <!-- Glow -->
                <circle cx="160" cy="120" r="130" fill="url(#glow)"/>
                <!-- Body -->
                <ellipse cx="160" cy="300" rx="90" ry="55" fill="url(#shirt)"/>
                <rect x="90" y="248" width="140" height="72" fill="url(#shirt)" rx="8"/>
                <!-- Collar -->
                <path d="M 140 248 L 160 272 L 180 248" fill="#1e1b4b" stroke="#4c1d95" stroke-width="1"/>
                <!-- Neck -->
                <rect x="143" y="196" width="34" height="32" fill="url(#face)" rx="6"/>
                <!-- Head -->
                <ellipse cx="160" cy="172" rx="58" ry="62" fill="url(#face)"/>
                <!-- Hair -->
                <path d="M 102 160 Q 104 105 160 100 Q 216 105 218 160 Q 200 130 160 128 Q 120 130 102 160Z" fill="#1a1a2e"/>
                <ellipse cx="160" cy="110" rx="58" ry="20" fill="#1a1a2e"/>
                <!-- Eyes brows -->
                <path d="M 132 156 Q 142 150 152 156" stroke="#5c3d2e" stroke-width="2.5" fill="none" stroke-linecap="round"/>
                <path d="M 168 156 Q 178 150 188 156" stroke="#5c3d2e" stroke-width="2.5" fill="none" stroke-linecap="round"/>
                <!-- Eyes -->
                <ellipse cx="142" cy="168" rx="9" ry="9.5" fill="white"/>
                <ellipse cx="178" cy="168" rx="9" ry="9.5" fill="white"/>
                <circle cx="144" cy="170" r="5.5" fill="#312e81"/>
                <circle cx="180" cy="170" r="5.5" fill="#312e81"/>
                <circle cx="146" cy="168" r="2" fill="white"/>
                <circle cx="182" cy="168" r="2" fill="white"/>
                <!-- Nose -->
                <path d="M 158 177 Q 155 185 162 186" stroke="#d4a373" stroke-width="1.5" fill="none" stroke-linecap="round"/>
                <!-- Smile -->
                <path d="M 148 194 Q 160 204 172 194" stroke="#c0824a" stroke-width="2.5" fill="none" stroke-linecap="round"/>
                <!-- Code badge -->
                <rect x="120" y="258" width="80" height="26" rx="7" fill="rgba(99,102,241,0.25)" stroke="rgba(129,140,248,0.4)" stroke-width="1"/>
                <text x="160" y="275" text-anchor="middle" fill="#a5b4fc" font-family="monospace" font-size="9.5" font-weight="700">&lt;/fullstack&gt;</text>
                <!-- Floating elements -->
                <text x="22" y="76" fill="rgba(99,102,241,0.35)" font-family="monospace" font-size="13" font-weight="600">{ }</text>
                <text x="265" y="94" fill="rgba(167,139,250,0.35)" font-family="monospace" font-size="12">fn()</text>
                <text x="25" y="250" fill="rgba(52,211,153,0.35)" font-family="monospace" font-size="11">npm</text>
                <text x="258" y="274" fill="rgba(96,165,250,0.35)" font-family="monospace" font-size="11">git</text>
              </svg>
            </div>

            <!-- Floating skill chips -->
            <div class="absolute -top-6 -right-8 glass border border-indigo-500/20 rounded-2xl px-4 py-2.5 text-xs font-bold text-indigo-300 shadow-2xl backdrop-blur-xl animate-float">
              Vue.js ⚡
            </div>
            <div class="absolute -bottom-6 -left-8 glass border border-violet-500/20 rounded-2xl px-4 py-2.5 text-xs font-bold text-violet-300 shadow-2xl backdrop-blur-xl animate-float2">
              Node.js 🚀
            </div>
          </div>

          <!-- Info pills row -->
          <div class="flex flex-wrap justify-center gap-2">
            <div v-for="p in pills" :key="p" class="flex items-center gap-1.5 px-3.5 py-2 glass border border-white/[0.06] rounded-full text-xs text-slate-400">
              {{ p }}
            </div>
          </div>
        </div>

        <!-- Text column -->
        <div class="reveal space-y-8">
          <div class="space-y-5 text-slate-400 text-lg leading-loose">
            <p>
              Diplômé d'un <span class="text-white font-semibold">Master of Science</span> à Supinfo (spécialité Intelligence Artificielle),
              je conçois des produits numériques qui allient performance technique et expérience utilisateur soignée.
            </p>
            <p>
              Du frontend réactif avec <span class="text-indigo-300 font-medium">Vue 3</span>
              au backend scalable avec <span class="text-indigo-300 font-medium">Node.js</span>,
              en passant par l'intégration d'ERP et la mise en place de pipelines CI/CD robustes —
              j'aime toucher à tous les niveaux de la stack.
            </p>
            <p>
              Curieux et rigoureux, je porte une attention particulière
              à la <span class="text-white font-medium">qualité du code</span>,
              à la <span class="text-white font-medium">maintenabilité</span>
              et à l'impact réel de chaque ligne produite.
            </p>
          </div>

          <!-- Stats grid -->
          <div class="grid grid-cols-2 gap-4 pt-2 max-w-md">
            <div
              v-for="s in statCards"
              :key="s.label"
              class="card p-5 text-center"
            >
              <div class="text-3xl font-black grad-blue mb-1">{{ s.value }}</div>
              <div class="text-slate-600 text-xs font-medium uppercase tracking-wider">{{ s.label }}</div>
            </div>
          </div>

          <!-- Link row -->
          <div class="flex flex-wrap gap-3 pt-2">
            <a href="https://www.linkedin.com/in/timothee-lefebvre/" target="_blank" class="btn-ghost text-sm py-2.5 px-5">
              <Linkedin :size="16" /> LinkedIn
            </a>
            <a href="mailto:leftim59@hotmail.fr" class="btn-ghost text-sm py-2.5 px-5">
              <Mail :size="16" /> leftim59@hotmail.fr
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Linkedin, Mail } from 'lucide-vue-next'

const pills = [
  '📍 Erquinghem-Lys, Nord',
  '🎓 Master Supinfo 2025',
  '💼 Freelance disponible',
  '🌍 Remote OK',
]

const statCards = [
  { value: '4+', label: 'Ans d\'exp.' },
  { value: '5+', label: 'Projets' },
]
</script>
