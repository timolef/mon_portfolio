<template>
  <section id="contact" class="relative py-36 overflow-hidden noise">
    <div class="absolute inset-0 bg-[#02040a]"></div>
    <div class="orb w-[600px] h-[600px] bg-indigo-700/[0.06] bottom-[-150px] left-[-100px]"></div>
    <div class="orb w-[400px] h-[400px] bg-violet-600/[0.05] top-[-100px] right-[-100px]"></div>
    <div class="divider"></div>

    <div class="relative z-10 max-w-6xl mx-auto px-6">
      <!-- Header -->
      <div class="section-header reveal">
        <div class="section-badge">📬 Contact</div>
        <h2 class="display-lg text-white">
          Travaillons <span class="grad-blue">ensemble</span>
        </h2>
        <p class="text-slate-400 text-lg max-w-2xl mx-auto mt-4">
          Un projet, une opportunité ou simplement envie d'échanger ? Je suis à un message de vous.
          <span class="text-slate-300 font-medium">Réponse sous 24h garantie.</span>
        </p>
      </div>

      <div class="grid lg:grid-cols-5 gap-10">
        <!-- Left: contacts -->
        <div class="lg:col-span-2 reveal-left space-y-4">
          <a
            v-for="info in contactInfos"
            :key="info.label"
            :href="info.href || undefined"
            :target="info.href ? '_blank' : undefined"
            :class="['card p-5 flex items-start gap-4 group', info.href ? 'cursor-pointer' : 'cursor-default']"
          >
            <div class="w-11 h-11 rounded-2xl flex items-center justify-center text-white shrink-0 shadow-xl group-hover:scale-110 transition-transform duration-300" :style="{ background: info.gradient }">
              <component :is="info.icon" :size="19" />
            </div>
            <div>
              <p class="text-slate-600 text-[10px] font-bold uppercase tracking-widest mb-1">{{ info.label }}</p>
              <p class="text-slate-200 font-medium text-sm break-all">{{ info.value }}</p>
            </div>
          </a>

          <!-- Availability -->
          <div class="card p-6 border-emerald-500/15 relative overflow-hidden">
            <div class="absolute inset-0 bg-gradient-to-br from-emerald-500/[0.03] to-transparent"></div>
            <div class="relative z-10">
              <div class="flex items-center gap-2.5 mb-3">
                <span class="relative flex h-2.5 w-2.5">
                  <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-400 opacity-60"></span>
                  <span class="relative rounded-full h-2.5 w-2.5 bg-emerald-500"></span>
                </span>
                <span class="text-emerald-400 font-bold text-sm">Disponible maintenant</span>
              </div>
              <p class="text-slate-500 text-sm leading-relaxed">
                CDI, CDD, missions freelance.<br>
                <span class="text-slate-300 font-medium">Nord de France</span> · Remote OK
              </p>
            </div>
          </div>
        </div>

        <!-- Right: form -->
        <div class="lg:col-span-3 reveal">
          <form @submit.prevent="handleSubmit" class="card p-8 lg:p-10 space-y-5">
            <div class="grid sm:grid-cols-2 gap-5">
              <div class="space-y-2">
                <label class="text-slate-500 text-[10px] font-bold uppercase tracking-widest">Nom complet</label>
                <input
                  v-model="form.name"
                  type="text"
                  placeholder="Jean Dupont"
                  required
                  class="form-input"
                />
              </div>
              <div class="space-y-2">
                <label class="text-slate-500 text-[10px] font-bold uppercase tracking-widest">Email</label>
                <input
                  v-model="form.email"
                  type="email"
                  placeholder="vous@exemple.fr"
                  required
                  class="form-input"
                />
              </div>
            </div>

            <div class="space-y-2">
              <label class="text-slate-500 text-[10px] font-bold uppercase tracking-widest">Sujet</label>
              <select v-model="form.subject" class="form-input appearance-none cursor-pointer">
                <option value="">Sélectionner un sujet</option>
                <option>Opportunité CDI / CDD</option>
                <option>Mission Freelance</option>
                <option>Collaboration projet</option>
                <option>Autre</option>
              </select>
            </div>

            <div class="space-y-2">
              <label class="text-slate-500 text-[10px] font-bold uppercase tracking-widest">Message</label>
              <textarea
                v-model="form.message"
                rows="5"
                placeholder="Décrivez votre projet ou votre besoin..."
                required
                class="form-input resize-none"
              ></textarea>
            </div>

            <button
              type="submit"
              :disabled="sending"
              :class="[
                'w-full flex items-center justify-center gap-2.5 py-4 rounded-2xl font-bold text-white text-sm transition-all duration-300 relative overflow-hidden',
                sent
                  ? 'bg-emerald-600 shadow-lg shadow-emerald-500/25'
                  : 'bg-gradient-to-r from-indigo-600 to-violet-600 hover:from-indigo-500 hover:to-violet-500 hover:shadow-xl hover:shadow-indigo-500/25 hover:-translate-y-0.5'
              ]"
            >
              <template v-if="!sending && !sent">
                <Send :size="17" />
                Envoyer le message
              </template>
              <template v-if="sending">
                <div class="w-4 h-4 border-2 border-white/30 border-t-white rounded-full animate-spin"></div>
                Envoi en cours...
              </template>
              <template v-if="sent">
                <Check :size="17" />
                Message envoyé avec succès !
              </template>
            </button>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import { Mail, Phone, Linkedin, MapPin, Send, Check } from 'lucide-vue-next'

const form = ref({ name: '', email: '', subject: '', message: '' })
const sending = ref(false)
const sent = ref(false)

const contactInfos = [
  { label: 'Email', value: 'leftim59@hotmail.fr', href: 'mailto:leftim59@hotmail.fr', icon: Mail, gradient: 'linear-gradient(135deg,#312e81,#4f46e5)' },
  { label: 'Téléphone', value: '07 81 70 77 69', href: 'tel:+33781707769', icon: Phone, gradient: 'linear-gradient(135deg,#064e3b,#059669)' },
  { label: 'LinkedIn', value: 'timothee-lefebvre', href: 'https://www.linkedin.com/in/timothee-lefebvre/', icon: Linkedin, gradient: 'linear-gradient(135deg,#1e3a8a,#2563eb)' },
  { label: 'Localisation', value: 'Erquinghem-Lys, Nord (59)', href: null, icon: MapPin, gradient: 'linear-gradient(135deg,#4c1d95,#7c3aed)' },
]

async function handleSubmit() {
  sending.value = true
  await new Promise(r => setTimeout(r, 2000))
  sending.value = false
  sent.value = true
  form.value = { name: '', email: '', subject: '', message: '' }
  setTimeout(() => (sent.value = false), 4500)
}
</script>

<style scoped>
.form-input {
  width: 100%;
  padding: 0.75rem 1rem;
  background: rgba(255,255,255,0.025);
  border: 1px solid rgba(255,255,255,0.06);
  border-radius: 14px;
  color: #e2e8f0;
  font-size: 0.875rem;
  transition: all 0.2s ease;
}
.form-input::placeholder { color: #334155; }
.form-input:focus {
  outline: none;
  border-color: rgba(99,102,241,0.5);
  background: rgba(255,255,255,0.04);
  box-shadow: 0 0 0 3px rgba(99,102,241,0.1);
}
</style>
