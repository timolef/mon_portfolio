<template>
  <section id="experience" class="relative py-36 overflow-hidden noise">
    <div class="absolute inset-0 bg-[#030610]"></div>
    <div class="orb w-[600px] h-[600px] bg-blue-700/[0.05] bottom-0 right-[-200px]"></div>
    <div class="divider"></div>

    <div class="relative z-10 max-w-6xl mx-auto px-6">
      <!-- Header -->
      <div class="section-header reveal">
        <div class="section-badge">💼 Parcours</div>
        <h2 class="display-lg text-white">
          Mon <span class="grad-blue">expérience</span>
        </h2>
      </div>

      <!-- Timeline -->
      <div class="relative">
        <!-- Vertical line -->
        <div class="absolute left-5 md:left-1/2 top-0 bottom-0 w-px bg-gradient-to-b from-indigo-500/40 via-violet-500/20 to-transparent md:-translate-x-[0.5px]"></div>

        <div class="space-y-0">
          <div
            v-for="(exp, i) in experiences"
            :key="exp.company"
            class="relative reveal"
            :style="{ transitionDelay: (i * 100) + 'ms' }"
          >
            <!-- Connector dot -->
            <div class="absolute left-5 md:left-1/2 -translate-x-1/2 top-8 z-10">
              <div :class="['w-3 h-3 rounded-full border-2', exp.current ? 'bg-indigo-500 border-indigo-400 shadow-lg shadow-indigo-500/40' : 'bg-[#030610] border-slate-600']"></div>
            </div>

            <!-- Row -->
            <div :class="['flex flex-col md:flex-row items-start gap-4 md:gap-0 pb-16', i % 2 === 0 ? '' : 'md:flex-row-reverse']">
              <!-- Date side -->
              <div :class="['hidden md:flex md:w-1/2 items-start pt-6', i % 2 === 0 ? 'justify-end pr-14' : 'justify-start pl-14']">
                <div class="flex items-center gap-3">
                  <span class="text-sm text-slate-500 font-mono bg-white/[0.03] px-3 py-1.5 rounded-lg border border-white/[0.05]">{{ exp.period }}</span>
                  <span v-if="exp.current" class="h-5 flex items-center px-2 bg-emerald-500/10 border border-emerald-500/25 rounded-md text-[10px] font-bold text-emerald-400 uppercase tracking-wider">En poste</span>
                </div>
              </div>

              <!-- Card side -->
              <div :class="['md:w-1/2 pl-14 md:pl-0', i % 2 === 0 ? 'md:pl-14' : 'md:pr-14']">
                <div :class="['card p-7 relative group', exp.current ? 'border-indigo-500/20 glow-indigo' : '']">
                  <!-- Mobile date -->
                  <div class="flex items-center gap-2 mb-4 md:hidden">
                    <span class="text-xs text-slate-500 font-mono">{{ exp.period }}</span>
                    <span v-if="exp.current" class="px-1.5 py-0.5 bg-emerald-500/10 border border-emerald-500/20 rounded text-[9px] font-bold text-emerald-400">En poste</span>
                  </div>

                  <!-- Top row -->
                  <div class="flex items-start gap-4 mb-5">
                    <div class="w-12 h-12 rounded-2xl flex items-center justify-center text-xl shrink-0 shadow-lg" :style="{ background: exp.gradient }">
                      {{ exp.emoji }}
                    </div>
                    <div>
                      <h3 class="text-white font-bold text-base leading-snug">{{ exp.title }}</h3>
                      <p class="text-indigo-400 font-semibold text-sm mt-0.5">{{ exp.company }}</p>
                    </div>
                  </div>

                  <!-- Tags -->
                  <div class="flex flex-wrap gap-1.5 mb-5">
                    <span v-for="tag in exp.tags" :key="tag" class="tag text-[11px]">{{ tag }}</span>
                  </div>

                  <!-- Achievements -->
                  <ul class="space-y-2.5">
                    <li v-for="a in exp.achievements" :key="a" class="flex items-start gap-2.5 text-slate-400 text-sm leading-relaxed">
                      <ChevronRight :size="14" class="text-indigo-500 mt-0.5 shrink-0" />
                      <span>{{ a }}</span>
                    </li>
                  </ul>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Education card -->
      <div class="mt-10 reveal">
        <div class="card p-10 text-center max-w-2xl mx-auto relative overflow-hidden">
          <div class="absolute inset-0 bg-gradient-to-br from-violet-500/[0.04] to-indigo-500/[0.02]"></div>
          <div class="relative z-10">
            <div class="text-5xl mb-5">🎓</div>
            <h3 class="text-white font-bold text-2xl mb-2">Master of Science</h3>
            <p class="text-indigo-400 font-bold text-base mb-2">Intelligence Artificielle</p>
            <p class="text-slate-500 font-medium text-sm mb-6">Supinfo Paris · 2025</p>
            <div class="flex flex-wrap justify-center gap-2">
              <span v-for="t in eduTags" :key="t" class="tag text-[11px]">{{ t }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ChevronRight } from 'lucide-vue-next'

const eduTags = ['IA & Machine Learning', 'Architecture logicielle', 'JavaScript Avancé', 'Cloud & DevOps', 'Gestion de projet']

const experiences = [
  {
    title: 'Développeur Fullstack',
    company: 'Association 48 pour 100',
    period: '2024 – Présent',
    emoji: '🏢',
    current: true,
    gradient: 'linear-gradient(135deg, #312e81, #4f46e5)',
    tags: ['Vue.js', 'Node.js', 'CI/CD', 'Docker'],
    achievements: [
      'Développement complet du site web et de l\'application mobile',
      'Mise en place de l\'architecture frontend et backend',
      'Automatisation des déploiements via pipeline CI/CD',
      'Maintenance, monitoring et évolutions fonctionnelles',
    ],
  },
  {
    title: 'Responsable Développement Web',
    company: 'Matériel-Médical.com',
    period: '2025',
    emoji: '⚕️',
    current: false,
    gradient: 'linear-gradient(135deg, #064e3b, #059669)',
    tags: ['WooCommerce', 'ERP', 'API SOAP', 'B2B'],
    achievements: [
      'Pilotage de la plateforme e-commerce B2B (+50k produits)',
      'Intégration ERP via API SOAP pour synchronisation temps réel',
      'Analyse et traduction des besoins métiers en spécifications techniques',
    ],
  },
  {
    title: 'Développeur Fullstack — Freelance',
    company: 'Indépendant',
    period: '2023 – Présent',
    emoji: '🚀',
    current: true,
    gradient: 'linear-gradient(135deg, #4c1d95, #7c3aed)',
    tags: ['Vue.js', 'Node.js', 'Docker', 'Architecture'],
    achievements: [
      'Applications web sur-mesure pour startups et PME',
      'Conception d\'architectures scalables et maintenables',
      'Optimisation e-commerce B2B WooCommerce connecté à un ERP',
      'Mise en place CI/CD + stratégie de tests automatisés',
    ],
  },
  {
    title: 'Développeur Fullstack',
    company: 'Euranov',
    period: '2022',
    emoji: '🎭',
    current: false,
    gradient: 'linear-gradient(135deg, #92400e, #d97706)',
    tags: ['React', 'Node.js', 'Back-office', 'API'],
    achievements: [
      'Feature de réservation pour l\'Accor Arena (5000+ places)',
      'Création du back-office d\'administration complet',
      'Travail en équipe agile (daily, sprints, retrospectives)',
    ],
  },
  {
    title: 'Assistant Informatique',
    company: 'GHICL',
    period: '2019',
    emoji: '🏥',
    current: false,
    gradient: 'linear-gradient(135deg, #1e3a5f, #2563eb)',
    tags: ['Python', 'PHP', 'Support'],
    achievements: [
      'Support technique aux équipes hospitalières',
      'Développement de scripts d\'automatisation (Python, PHP)',
    ],
  },
]
</script>
