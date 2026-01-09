<script setup lang="ts">
import { onMounted } from 'vue'
import { ref } from 'vue'

const copiedPhone = ref(false)


onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('show')
        }
      })
    },
    { threshold: 0.2 }
  )

  document.querySelectorAll('.reveal').forEach((el) => {
    observer.observe(el)
  })
})

function copyPhone() {
  navigator.clipboard.writeText('6530232243')
  copiedPhone.value = true

  setTimeout(() => {
    copiedPhone.value = false
  }, 2000)
}
</script>

<template>
  <section class="min-h-screen w-screen bg-slate-900 flex items-center justify-center px-6">
    <div class="max-w-5xl w-full">

      <div class="text-center mb-20 reveal">
        <h1 class="font-bebas text-6xl text-amber-400 tracking-wide mb-6">
          Contato
        </h1>
      </div>

      <div class="reveal bg-white/5 backdrop-blur-md border border-white/10 rounded-2xl p-12 shadow-2xl">
        <div class="grid md:grid-cols-2 gap-12">


          <div class="space-y-4 reveal">
            <h2 class="font-bebas text-3xl text-white tracking-wide">
              Endereço
            </h2>

            <a href="https://www.google.com/maps/search/?api=1&query=Av.+Isaac+Póvoas,+1331,+Cuiabá+MT" target="_blank"
              class="block text-slate-300 leading-relaxed hover:text-amber-400 transition-colors duration-300">
              Bairro Popular<br />
              Condomínio Edifício Milão<br />
              Av. Isaac Póvoas, 1331<br />
              Sala 33, 3º Andar
            </a>
          </div>



          <div class="space-y-6">
            <h2 class="font-bebas text-3xl text-white tracking-wide reveal">
              Nossas redes e contatos
            </h2>

            <a href="https://www.instagram.com/omadvogadoss?igsh=MTlrYjU0Ymhpa2g3Yg==" target="_blank"
              class="reveal flex items-center gap-4 text-slate-300 hover:text-amber-400 transition-all duration-300 hover:translate-x-2">
              <div class="w-12 h-12 flex items-center justify-center">

                <span class="iconify w-8 h-8" data-icon="mdi:instagram"></span>

              </div>
              <span>@omadvogados</span>
            </a>

            <div
              class="reveal flex items-center gap-4 text-slate-300 hover:text-amber-400 transition-all duration-300 hover:translate-x-2">
              <a href="https://mail.google.com/mail/u/0/?fs=1&tf=cm&source=mailto&to=contato@omadvogados.com"
                target="_blank"
                class="reveal flex items-center gap-4 text-slate-300 hover:text-amber-400 transition-all duration-300 hover:translate-x-2">
                <div class="w-12 h-12 flex items-center justify-center">
                  <span class="iconify w-8 h-8" data-icon="streamline-logos:email-logo"></span>
                </div>
                <span>contato@omadvogados.com</span>
              </a>
            </div>

            <div class=" reveal flex items-center gap-4 text-slate-300 hover:text-amber-400 transition-all duration-300
                  hover:translate-x-2">
              <a href="https://wa.me/81060009" target="_blank"
                class="reveal flex items-center gap-4 text-slate-300 hover:text-amber-400 transition-all duration-300 hover:translate-x-2">
                <div class="w-12 h-12 flex items-center justify-center">
                  <span class="iconify w-8 h-8" data-icon="ic:baseline-whatsapp"></span>
                </div>
                <span>(65) 98106-0009</span>
              </a>
            </div>

            <div
              class="reveal flex items-center gap-4 cursor-pointer text-slate-300 hover:text-amber-400 transition-all duration-300 hover:translate-x-2"
              @click="copyPhone">
              <div class="w-12 h-12 flex items-center justify-center">
                <span class="iconify w-8 h-8" data-icon="carbon:phone-ip"></span>
              </div>

              <span>(65) 3023-2243</span>

              <span v-if="copiedPhone" class="ml-2 text-sm text-amber-400">
                Copiado
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style>
.reveal {
  opacity: 0;
  transform: translateY(40px);
  transition: all 0.8s ease;
}

.reveal.show {
  opacity: 1;
  transform: translateY(0);
}
</style>
