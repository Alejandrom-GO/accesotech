<template>
        <!-- Servicios Section -->
        <section id="servicios" class="py-24 relative">
            <div class="container mx-auto px-4 relative z-10">
              <div class="text-center mb-16">
                <h2 class="text-5xl font-bold text-gray-800 mb-12">¿Qué hacemos?</h2>
                <p class="text-2xl text-gray-600 max-w-2xl mx-auto">Ofrecemos soluciones tecnológicas personalizadas que se ajustan a las necesidades de cada cliente.</p>
              </div>
              <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <div v-for="(servicio, index) in servicios" :key="index" 
                     class="inspira-card">
                  <div class="inspira-icon-container" :class="`icon-${index + 1}`">
                    <component :is="servicio.icon" class="w-8 h-8" />
                  </div>
                  <h3 class="text-xl font-bold text-gray-800 mb-3">{{ servicio.title }}</h3>
                  <p class="text-gray-600">{{ servicio.description }}</p>
                </div>
              </div>
            </div>
      </section>
      
</template>
<script setup>
import SvgSmartphone from '@/components/svg/SvgSmartphone.vue';
import SvgGlobe from '@/components/svg/SvgGlobe.vue';
import SvgSettings from '@/components/svg/SvgSettings.vue';
import SvgLayout from '@/components/svg/SvgLayout.vue';
import SvgLink from '@/components/svg/SvgLink.vue';

const servicios = ref([
  {
    title: 'Desarrollo de aplicaciones móviles',
    description: 'Creamos apps nativas y multiplataforma con Flutter, diseñadas para ofrecer una experiencia de usuario excepcional.',
    icon: SvgSmartphone
  },
  {
    title: 'Plataformas web personalizadas',
    description: 'Desarrollamos plataformas web a medida que se adaptan perfectamente a los procesos específicos de tu negocio.',
    icon: SvgGlobe
  },
  {
    title: 'Sistemas internos de gestión',
    description: 'Automatizamos tus procesos de ventas, inventarios, facturación y más con sistemas intuitivos y eficientes.',
    icon: SvgSettings
  },
  {
    title: 'Sitios web profesionales',
    description: 'Diseñamos y desarrollamos sitios web que representan profesionalmente tu marca y generan confianza.',
    icon: SvgLayout
  },
  {
    title: 'Integraciones con herramientas externas',
    description: 'Conectamos tus sistemas con APIs, pasarelas de pago y otras herramientas para crear flujos de trabajo sin fricciones.',
    icon: SvgLink
  }
]);
</script>