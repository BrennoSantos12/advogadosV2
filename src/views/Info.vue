<script setup lang="ts">
import { onMounted } from "vue"


onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        entry.target.classList.add("show")
      } else {
        entry.target.classList.remove("show");
      }
    })
  })

  const todosTexto = document.querySelectorAll('.texto')
  todosTexto.forEach(el => observer.observe(el))
})
</script>


<template>
  <div class="min-h-screen w-screen bg-slate-900 text-slate-100">
    <div class="flex flex-col mx-auto max-w-5xl px-6 pt-24">

      <div class="flex justify-center">
        <h1 class="text-5xl font-bebas mb-16 text-amber-400 texto">
          Como vamos te ajudar
        </h1>
      </div>

      <div class="bloco">
        <h2 class="titulo texto text-2xl font-semibold text-amber-300">
          Direito Empresarial
        </h2>
        <p class="paragrafo texto text-lg leading-relaxed text-slate-300">
          Atuação na defesa dos interesses da empresa e do empresário,
          auxiliando na tomada de decisões e no contencioso cível,
          tributário e trabalhista.
        </p>
      </div>

      <div class="bloco">
        <h2 class="titulo texto text-2xl font-semibold text-amber-300">
          Recuperação de Crédito e Cobrança
        </h2>
        <p class="paragrafo texto text-lg leading-relaxed text-slate-300">
          Atua de forma extrajudicial e judicial reavendo valores devidos à empresa
          e não pagos, com a maior celeridade e sucesso.
        </p>
      </div>

      <div class="bloco">
        <h2 class="titulo texto text-2xl font-semibold text-amber-300">
          Direito Civil e do Consumidor
        </h2>
        <p class="paragrafo texto text-lg leading-relaxed text-slate-300">
          Trabalhamos na defesa dos direitos privados, de propriedade, obrigações,
          família e das relações de consumo (bens e serviços).
        </p>
      </div>

      <div class="bloco">
        <h2 class="titulo texto text-2xl font-semibold text-amber-300">
          Direito do Trabalho e Previdenciário
        </h2>
        <p class="paragrafo texto text-lg leading-relaxed text-slate-300">
          Atua nas ações decorrentes da relação de trabalho em todas as suas espécies,
          bem como no ramo do direito que envolve a seguridade social com foco no
          direito aos benefícios e aposentadoria.
        </p>
      </div>

      <div class="bloco">
        <h2 class="titulo texto text-2xl font-semibold text-amber-300">
          Direito Fiscal e Tributário
        </h2>
        <p class="paragrafo texto text-lg leading-relaxed text-slate-300">
          Atua no planejamento, recuperação de valores, e defesa dos contribuintes
          pagadores de impostos, frente a suas obrigações junto ao Estado
          (União, Estado e/ou Município).
        </p>
      </div>

      <div class="bloco mb-20">
        <h2 class="titulo texto text-2xl font-semibold text-amber-300">
          Direito Administrativo e Eleitoral
        </h2>
        <p class="paragrafo texto text-lg leading-relaxed text-slate-300">
          Atua junto a autarquias, órgãos da administração pública e privadas que
          possuam relação com a administração pública na regulação das atividades
          com o fim de interesses públicos. Atua na defesa dos direitos políticos
          e partidários.
        </p>
      </div>

    </div>
  </div>
</template>


<style>
.texto {
  opacity: 0;
  transform: translateY(100px);
  transition: opacity 1s ease,
    transform 1s ease;
}

.show {
  opacity: 1;
  transform: translateY(0px);
}


.bloco {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  max-width: 520px;
}

.bloco:nth-of-type(even) {
  margin-left: auto;
  text-align: right;
}
</style>
