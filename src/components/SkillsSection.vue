<template>
  <section id="skills" class="relative py-36 overflow-hidden noise">
    <div class="absolute inset-0 bg-[#02040a]"></div>
    <div class="orb w-[600px] h-[600px] bg-violet-700/6 top-[-100px] left-[-200px]"></div>
    <div class="divider"></div>

    <div class="relative z-10 max-w-7xl mx-auto px-6">
      <!-- Header -->
      <div class="section-header reveal">
        <div class="section-badge">⚡ Stack technique</div>
        <h2 class="display-lg text-white">
          Ce que je<br>
          <span class="grad-blue">maîtrise</span>
        </h2>
      </div>

      <!-- Category tabs -->
      <div class="flex flex-wrap justify-center gap-2 mb-16 reveal">
        <button
          v-for="cat in categories"
          :key="cat.id"
          @click="active = cat.id"
          :class="[
            'px-5 py-2.5 rounded-xl text-sm font-semibold transition-all duration-300',
            active === cat.id
              ? 'bg-gradient-to-r from-indigo-600 to-violet-600 text-white shadow-lg shadow-indigo-500/20'
              : 'glass border border-white/[0.06] text-slate-500 hover:text-slate-200 hover:border-white/[0.12]'
          ]"
        >{{ cat.icon }}&nbsp; {{ cat.label }}</button>
      </div>

      <!-- Skill cards grid -->
      <TransitionGroup name="skills-fade" tag="div" class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4">
        <div
          v-for="skill in filtered"
          :key="skill.name"
          class="card p-6 group cursor-default"
        >
          <!-- Top row -->
          <div class="flex items-center justify-between mb-5">
            <div class="flex items-center gap-3.5">
              <div
                class="w-11 h-11 rounded-xl flex items-center justify-center text-xl shrink-0 shadow-lg"
                :style="{ background: skill.bg }"
              >{{ skill.icon }}</div>
              <div>
                <h3 class="text-white font-bold text-sm">{{ skill.name }}</h3>
                <span :class="['text-xs font-semibold', levelCls[skill.level]]">{{ skill.level }}</span>
              </div>
            </div>
            <span class="text-[11px] text-slate-600 font-mono bg-white/[0.04] px-2.5 py-1 rounded-lg">{{ skill.years }}</span>
          </div>

          <!-- Progress -->
          <div class="relative h-1 bg-white/[0.05] rounded-full overflow-hidden mb-2">
            <div
              class="absolute left-0 top-0 h-full rounded-full transition-all duration-1000 ease-out"
              :style="{ width: skill.pct + '%', background: skill.color }"
            ></div>
          </div>
          <div class="flex justify-between items-center">
            <span class="text-slate-600 text-xs">{{ skill.desc }}</span>
            <span class="text-slate-600 text-[11px] font-mono">{{ skill.pct }}%</span>
          </div>
        </div>
      </TransitionGroup>

      <!-- Tag cloud section -->
      <div class="mt-24 reveal">
        <p class="text-center text-slate-600 text-sm font-medium uppercase tracking-widest mb-8">Écosystème élargi</p>
        <div class="flex flex-wrap justify-center gap-2.5">
          <span v-for="t in extraTags" :key="t" class="tag cursor-default">{{ t }}</span>
        </div>
      </div>

      <!-- Bottom highlights -->
      <div class="grid sm:grid-cols-3 gap-5 mt-20 reveal">
        <div v-for="h in highlights" :key="h.title" class="card p-7 text-center">
          <div class="text-4xl mb-4">{{ h.emoji }}</div>
          <h3 class="text-white font-bold text-lg mb-2">{{ h.title }}</h3>
          <p class="text-slate-500 text-sm leading-relaxed">{{ h.desc }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from 'vue'

const active = ref('all')

const categories = [
  { id: 'all', label: 'Toutes', icon: '✦' },
  { id: 'frontend', label: 'Frontend', icon: '🎨' },
  { id: 'backend', label: 'Backend', icon: '⚙️' },
  { id: 'data', label: 'Data & DB', icon: '🗄️' },
  { id: 'devops', label: 'DevOps', icon: '🚀' },
]

const levelCls = {
  Expert: 'text-emerald-400',
  Avancé: 'text-sky-400',
  Intermédiaire: 'text-violet-400',
}

const skills = [
  { name: 'Vue.js 3', icon: '💚', cat: 'frontend', level: 'Expert', years: '3 ans', pct: 93, desc: 'Vue 3, Pinia, Router, Vite', bg: 'linear-gradient(135deg,#064e3b,#065f46)', color: 'linear-gradient(90deg,#10b981,#34d399)' },
  { name: 'JavaScript', icon: '🟡', cat: 'frontend', level: 'Expert', years: '4 ans', pct: 95, desc: 'ES2024, TypeScript', bg: 'linear-gradient(135deg,#713f12,#78350f)', color: 'linear-gradient(90deg,#f59e0b,#fcd34d)' },
  { name: 'React.js', icon: '⚛️', cat: 'frontend', level: 'Avancé', years: '2 ans', pct: 78, desc: 'Hooks, Context, Next.js', bg: 'linear-gradient(135deg,#0c4a6e,#075985)', color: 'linear-gradient(90deg,#38bdf8,#7dd3fc)' },
  { name: 'HTML / CSS', icon: '🎨', cat: 'frontend', level: 'Expert', years: '4 ans', pct: 96, desc: 'Tailwind, Responsive, A11y', bg: 'linear-gradient(135deg,#7c2d12,#9a3412)', color: 'linear-gradient(90deg,#f97316,#fb923c)' },
  { name: 'Node.js', icon: '🟢', cat: 'backend', level: 'Expert', years: '3 ans', pct: 91, desc: 'Express, REST, JWT, WebSocket', bg: 'linear-gradient(135deg,#14532d,#166534)', color: 'linear-gradient(90deg,#22c55e,#4ade80)' },
  { name: 'PHP', icon: '🐘', cat: 'backend', level: 'Intermédiaire', years: '2 ans', pct: 66, desc: 'WordPress, WooCommerce', bg: 'linear-gradient(135deg,#2e1065,#3b0764)', color: 'linear-gradient(90deg,#a855f7,#c084fc)' },
  { name: 'Python', icon: '🐍', cat: 'backend', level: 'Intermédiaire', years: '2 ans', pct: 62, desc: 'Scripts, AI, Automation', bg: 'linear-gradient(135deg,#172554,#1e3a5f)', color: 'linear-gradient(90deg,#60a5fa,#93c5fd)' },
  { name: 'SQL', icon: '🗄️', cat: 'data', level: 'Avancé', years: '3 ans', pct: 84, desc: 'MySQL, PostgreSQL, ORM', bg: 'linear-gradient(135deg,#0c4a6e,#164e63)', color: 'linear-gradient(90deg,#0ea5e9,#38bdf8)' },
  { name: 'NoSQL', icon: '🍃', cat: 'data', level: 'Avancé', years: '2 ans', pct: 76, desc: 'MongoDB, Redis, Firestore', bg: 'linear-gradient(135deg,#052e16,#14532d)', color: 'linear-gradient(90deg,#34d399,#6ee7b7)' },
  { name: 'Docker', icon: '🐳', cat: 'devops', level: 'Avancé', years: '2 ans', pct: 81, desc: 'Compose, Dockerfile, Registries', bg: 'linear-gradient(135deg,#0c4a6e,#1e40af)', color: 'linear-gradient(90deg,#3b82f6,#60a5fa)' },
  { name: 'CI/CD', icon: '🔄', cat: 'devops', level: 'Avancé', years: '2 ans', pct: 79, desc: 'GitHub Actions, GitLab CI', bg: 'linear-gradient(135deg,#7f1d1d,#991b1b)', color: 'linear-gradient(90deg,#ef4444,#f87171)' },
  { name: 'Git', icon: '🌿', cat: 'devops', level: 'Expert', years: '4 ans', pct: 92, desc: 'Flow, Rebase, PR Reviews', bg: 'linear-gradient(135deg,#431407,#7c2d12)', color: 'linear-gradient(90deg,#f97316,#fb923c)' },
]

const extraTags = ['API REST', 'GraphQL', 'WebSocket', 'WordPress', 'WooCommerce', 'ERP / SOAP', 'JWT', 'OAuth 2.0', 'NGINX', 'Linux', 'Postman', 'Vite', 'ESLint', 'Vitest', 'Figma', 'Vercel', 'Cloudflare', 'JSON / XML']

const filtered = computed(() =>
  active.value === 'all' ? skills : skills.filter(s => s.cat === active.value)
)

const highlights = [
  { emoji: '🏗️', title: 'Architecture first', desc: 'Je conçois des bases solides, modulaires et évolutives avant d\'écrire la première ligne de code.' },
  { emoji: '⚡', title: 'Performance obsédée', desc: 'Lighthouse > 90, bundle splitting, lazy loading — la performance n\'est pas une option.' },
  { emoji: '🔍', title: 'Code quality', desc: 'Tests unitaires, code review rigoureux, conventions ESLint / Prettier sur chaque projet.' },
]
</script>

<style scoped>
.skills-fade-move, .skills-fade-enter-active, .skills-fade-leave-active { transition: all 0.35s cubic-bezier(0.4,0,0.2,1); }
.skills-fade-enter-from, .skills-fade-leave-to { opacity: 0; transform: scale(0.94) translateY(10px); }
.skills-fade-leave-active { position: absolute; }
</style>
