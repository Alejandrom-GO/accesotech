<template>
    
    <!-- Footer -->
    <footer class="pt-24 pb-12 relative overflow-hidden bg-gradient-to-r from-gray-900 to-gray-800">
        <div class="inspira-footer-decoration"></div>
        <div class="container mx-auto px-4 relative z-10">
          <div class="grid grid-cols-1 md:grid-cols-4 gap-12">
            <div v-motion :initial="{ opacity: 0, y: 30 }" :enter="{ opacity: 1, y: 0, transition: { duration: 800 } }">
              <div class="flex items-center space-x-2 mb-6">
                <div class="text-transparent bg-clip-text bg-gradient-to-r from-[#007BFF] to-[#00C896]">
                  <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-code"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg>
                </div>
                <span class="font-bold text-2xl text-transparent bg-clip-text bg-gradient-to-r from-[#007BFF] to-[#00C896]">Accesotech</span>
              </div>
              <p class="text-gray-400">Soluciones tecnológicas simples, efectivas y sin complicaciones para pequeñas y medianas empresas.</p>
            </div>
            <div v-motion :initial="{ opacity: 0, y: 30 }" :enter="{ opacity: 1, y: 0, transition: { delay: 200, duration: 800 } }">
              <h4 class="font-bold text-lg mb-6 text-white">Servicios</h4>
              <ul class="space-y-3">
                <li v-for="(item, index) in footerLinks.servicios" :key="index">
                  <a :href="item.href" class="inspira-footer-link">
                    {{ item.text }}
                  </a>
                </li>
              </ul>
            </div>
            <div v-motion :initial="{ opacity: 0, y: 30 }" :enter="{ opacity: 1, y: 0, transition: { delay: 400, duration: 800 } }">
              <h4 class="font-bold text-lg mb-6 text-white">Empresa</h4>
              <ul class="space-y-3">
                <li v-for="(item, index) in footerLinks.empresa" :key="index">
                  <a :href="item.href" class="inspira-footer-link">
                    {{ item.text }}
                  </a>
                </li>
              </ul>
            </div>
            <div v-motion :initial="{ opacity: 0, y: 30 }" :enter="{ opacity: 1, y: 0, transition: { delay: 600, duration: 800 } }">
              <h4 class="font-bold text-lg mb-6 text-white">Contacto</h4>
              <ul class="space-y-4">
                <li v-for="(item, index) in contactInfo" :key="index" class="inspira-contact-item">
                  <component :is="item.icon" class="inspira-contact-icon" />
                  {{ item.text }}
                </li>
              </ul>
            </div>
          </div>
          <div class="border-t border-gray-700 mt-16 pt-8 flex flex-col md:flex-row justify-between items-center">
            <p class="text-gray-400">© {{ new Date().getFullYear() }} Accesotech. Todos los derechos reservados.</p>
            <div class="flex space-x-6 mt-6 md:mt-0">
              <a href="#" class="text-gray-400 hover:text-white transition-colors">Política de Privacidad</a>
              <a href="#" class="text-gray-400 hover:text-white transition-colors">Términos de Servicio</a>
            </div>
          </div>
        </div>
      </footer>
</template>
<script setup>

// Footer links
const footerLinks = {
  servicios: [
    { text: 'Desarrollo de apps', href: '#' },
    { text: 'Plataformas web', href: '#' },
    { text: 'Sistemas de gestión', href: '#' },
    { text: 'Sitios web', href: '#' }
  ],
  empresa: [
    { text: 'Sobre nosotros', href: '#' },
    { text: 'Blog', href: '#' },
    { text: 'Casos de éxito', href: '#' },
    { text: 'Trabaja con nosotros', href: '#' }
  ]
};

// Contact info
const contactInfo = [
  { 
    text: '+123 456 7890',
    icon: 'svg-phone'
  },
  {
    text: 'info@accesotech.com',
    icon: 'svg-mail'
  },
  {
    text: 'Ciudad de México, México',
    icon: 'svg-map-pin'
  }
];

</script>