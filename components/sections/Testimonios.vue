<template>
        <!-- Testimonios Section -->
        <section id="testimonios" class="py-24 relative overflow-hidden">
            <div class="inspira-dots"></div>
            <div class="container mx-auto px-4 relative z-10">
              <div class="text-center mb-16" >
                <h2 class="text-4xl font-bold text-gray-800 mb-12">Lo que dicen nuestros clientes</h2>
                <p class="text-xl text-gray-600 max-w-2xl mx-auto">Empresas que ya han simplificado su tecnología con nosotros.</p>
              </div>
              <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div v-for="(testimonio, index) in testimonios" :key="index" 
                     class="inspira-testimonial-card">
                  <div class="inspira-stars">
                    <svg v-for="i in 5" :key="i" xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="currentColor" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-star"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
                  </div>
                  <p class="inspira-quote">"{{ testimonio.comment }}"</p>
                  <div class="flex items-center">
                    <div class="inspira-avatar">
                      <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-user"><path d="M19 21v-2a4 4 0 0 0-4-4H9a4 4 0 0 0-4 4v2"/><circle cx="12" cy="7" r="4"/></svg>
                    </div>
                    <div>
                      <h4 class="font-bold text-gray-800">{{ testimonio.name }}</h4>
                      <p class="text-gray-600">{{ testimonio.position }}</p>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </section>
</template>
<script setup>



// Testimonios data
const testimonios = ref([
  {
    name: 'Juan M.',
    position: 'Dueño de tienda de ropa',
    comment: 'Gracias a Accesotech ahora tengo control total de mis ventas desde el celular. ¡Súper fácil y confiable!'
  },
  {
    name: 'María L.',
    position: 'Gerente de restaurante',
    comment: 'Implementamos su sistema de pedidos online y nuestras ventas aumentaron un 30%. La plataforma es intuitiva y nuestros clientes la adoran.'
  },
  {
    name: 'Carlos R.',
    position: 'Consultor independiente',
    comment: 'Mi sitio web profesional me ha ayudado a conseguir nuevos clientes. El proceso fue sencillo y el resultado superó mis expectativas.'
  }
]);



</script>