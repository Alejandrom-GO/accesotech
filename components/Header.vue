<template>
    
    <!-- Header -->
    <header class="sticky top-0 z-50 transition-all duration-500" :class="{ 'py-2 bg-white/80 backdrop-blur-xl shadow-lg': scrolled, 'py-4 bg-transparent': !scrolled }">
        <div class="container mx-auto px-4 flex justify-between items-center">
          <div class="flex items-center space-x-2">
            <div class="text-transparent bg-clip-text bg-gradient-to-r from-[#007BFF] to-[#00C896]">
              <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-code"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg>
            </div>
            <span class="font-bold text-2xl text-transparent bg-clip-text bg-gradient-to-r from-[#007BFF] to-[#00C896]">Accesotech</span>
          </div>
          <nav class="hidden md:flex space-x-8">
            <a v-for="(item, index) in navItems" :key="index" :href="item.href" 
               class="text-gray-700 hover:text-transparent hover:bg-clip-text hover:bg-gradient-to-r hover:from-[#007BFF] hover:to-[#00C896] transition-all duration-300 font-medium">
              {{ item.text }}
            </a>
          </nav>
          <div class="md:hidden">
            <button @click="mobileMenuOpen = !mobileMenuOpen" class="text-gray-700 transition-transform duration-300" :class="{ 'rotate-90': mobileMenuOpen }">
              <svg v-if="!mobileMenuOpen" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-menu"><line x1="4" x2="20" y1="12" y2="12"/><line x1="4" x2="20" y1="6" y2="6"/><line x1="4" x2="20" y1="18" y2="18"/></svg>
              <svg v-else xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-x"><path d="M18 6 6 18"/><path d="m6 6 12 12"/></svg>
            </button>
          </div>
        </div>
        <!-- Mobile menu -->
        <div v-if="mobileMenuOpen" class="md:hidden bg-white/90 backdrop-blur-xl shadow-lg">
          <div class="container mx-auto px-4 py-4 flex flex-col space-y-4">
            <a v-for="(item, index) in navItems" :key="index" :href="item.href" 
               class="text-gray-700 py-2 hover:text-transparent hover:bg-clip-text hover:bg-gradient-to-r hover:from-[#007BFF] hover:to-[#00C896] transition-all duration-300 transform hover:translate-x-2 font-medium" 
               @click="mobileMenuOpen = false">
              {{ item.text }}
            </a>
          </div>
        </div>
      </header>
  
  
  
  
  
</template>

<script setup>
// Navigation items
const navItems = [
  { text: 'Servicios', href: '#servicios' },
  { text: 'Beneficios', href: '#beneficios' },
  { text: 'Proceso', href: '#proceso' },
  { text: 'Testimonios', href: '#testimonios' },
  { text: 'Contacto', href: '#contacto' }
];



</script>