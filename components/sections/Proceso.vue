<template>
        <!-- Proceso Section -->
        <section id="proceso" class="py-24 relative min-h-screen">
            <div class="container mx-auto px-4 relative z-10">
              <div class="text-center mb-16">
                <h2 class="text-5xl font-bold text-gray-800 mb-12">¿Cómo trabajamos?</h2>
                <p class="text-2xl text-gray-600 max-w-2xl mx-auto">Un proceso simple y claro, sin complicaciones.</p>
              </div>
              <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 relative">
                <!-- Línea de conexión -->
                <div class="inspira-process-line"></div>
                
                <div v-for="(paso, index) in proceso" :key="index" 
                     class="inspira-process-card">
                  <div class="inspira-process-number">
                    {{ index + 1 }}
                  </div>
                  <h3 class="text-xl font-bold text-gray-800 mb-3">{{ paso.title }}</h3>
                  <p class="text-gray-600">{{ paso.description }}</p>
                </div>
              </div>
            </div>
          </section>
</template>

<script setup>
// Proceso data
const proceso = ref([
  {
    title: 'Escuchamos tu necesidad',
    description: 'Agenda una llamada o reunión donde entendemos tu negocio y sus desafíos específicos.'
  },
  {
    title: 'Te proponemos una solución',
    description: 'Creamos una propuesta personalizada, clara y sin letra chiquita, adaptada a tus necesidades.'
  },
  {
    title: 'Desarrollamos tu sistema',
    description: 'Nuestro equipo se encarga de construir tu solución paso a paso, manteniéndote informado en todo momento.'
  },
  {
    title: 'Te acompañamos',
    description: 'Ofrecemos soporte y mejoras después de la entrega para que siempre estés cubierto y tu sistema evolucione.'
  }
]);


</script>