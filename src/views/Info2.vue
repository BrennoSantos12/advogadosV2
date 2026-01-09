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
  <section class="min-h-screen w-screen bg-stone-300 flex items-center">
    <div class="mx-auto max-w-4xl px-6 py-24">

      <!-- Título -->
      <h1 class="flex font-bebas text-6xl text-stone-900 mb-12 justify-center tracking-wide texto">
        O Escritório
      </h1>

      <!-- Conteúdo -->
      <div class="space-y-8 text-stone-700 text-lg leading-relaxed">

        <p class="texto">
          Fundado em 03 de outubro de 2008, o escritório
          <strong class="text-sky-800">Oliveira & Mascarenhas</strong>
          atua de forma sólida e estratégica em Cuiabá/MT e região, oferecendo assessoria
          jurídica completa e personalizada.
        </p>

        <p class="texto">
          Desde o início de suas atividades, o escritório tem como missão atender seus clientes
          e parceiros de maneira ampla, responsável e eficiente, sempre com foco em soluções
          práticas e resultados consistentes.
        </p>

        <p class="texto">
          Com atuação nas áreas de
          <strong class="text-sky-800">
            Direito Empresarial e Comercial, Direito Civil e do Consumidor,
            Recuperação de Crédito e Cobrança, Direito Trabalhista, Tributário e Penal
          </strong>,
          o escritório alia conhecimento técnico à visão de negócios.
        </p>

        <p class="texto">
          Ao longo dos anos, o
          <strong class="text-sky-800">Oliveira & Mascarenhas</strong>
          consolidou-se como um escritório confiável, pautado pela ética,
          comprometimento e excelência profissional.
        </p>

      </div>

    </div>
  </section>
</template>
