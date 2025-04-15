<template>
        <!-- Beneficios Section -->
        <section id="beneficios" class="py-24 relative overflow-hidden">
            <div class="inspira-pattern"></div>
            <div class="container mx-auto px-4 relative z-10">
              <div class="text-center mb-16">
                <h2 class="text-5xl font-bold text-gray-800 mb-12">¿Por qué elegir Accesotech?</h2>
                <p class="text-2xl text-gray-600 max-w-2xl mx-auto">Más que desarrollo, somos tu aliado tecnológico.</p>
              </div>
              <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div v-for="(beneficio, index) in beneficios" :key="index" 
                     class="inspira-benefit-card"
                    >
                  <div class="inspira-check-icon">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-check-circle"><path d="M22 11.08V12a10 10 0 1 1-5.93-9.14"/><path d="m9 11 3 3L22 4"/></svg>
                  </div>
                  <h3 class="text-xl font-bold text-gray-800 mb-3">{{ beneficio.title }}</h3>
                  <p class="text-gray-600">{{ beneficio.description }}</p>
                </div>
              </div>
            </div>
          </section>
</template>
<script setup> 

// Beneficios data
const beneficios = ref([
  {
    title: 'Soluciones a medida',
    description: 'No usamos plantillas genéricas. Cada solución se diseña específicamente para resolver tus necesidades particulares.'
  },
  {
    title: 'Precios accesibles para pymes',
    description: 'Ofrecemos tecnología de calidad a precios que se ajustan a la realidad de las pequeñas y medianas empresas.'
  },
  {
    title: 'Desarrollo rápido y enfocado',
    description: 'Nos centramos en entregar valor rápidamente, con ciclos de desarrollo ágiles y entregas incrementales.'
  },
  {
    title: 'Acompañamiento continuo',
    description: 'Te acompañamos durante todo el proceso, desde la idea inicial hasta el soporte posterior al lanzamiento.'
  },
  {
    title: 'Comunicación clara y cercana',
    description: 'Hablamos tu idioma, sin jerga técnica innecesaria, para que entiendas exactamente lo que estamos haciendo.'
  }
]);


</script>