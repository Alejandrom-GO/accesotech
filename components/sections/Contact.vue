<template>
    
    <!-- Contact Section -->
    <section id="contacto" class="py-24 relative overflow-hidden">
        <div class="container mx-auto px-4 relative z-10">
          <div class="text-center mb-16">
            <h2 class="text-5xl font-bold text-gray-800 mb-12">¿Tienes una idea o necesitas una solución para tu negocio?</h2>
            <p class="text-2xl text-gray-600 max-w-2xl mx-auto">Hablemos. Estamos listos para ayudarte.</p>
          </div>
          <div class="inspira-contact-container">
            <form @submit.prevent="submitForm" class="grid grid-cols-1 md:grid-cols-2 gap-6">
              <div class="md:col-span-1">
                <label for="name" class="block text-gray-700 mb-2 font-medium">Nombre</label>
                <div class="relative">
                  <input type="text" id="name" v-model="contactForm.name" 
                         class="inspira-input" 
                         required />
                </div>
              </div>
              <div class="md:col-span-1">
                <label for="email" class="block text-gray-700 mb-2 font-medium">Email</label>
                <div class="relative">
                  <input type="email" id="email" v-model="contactForm.email" 
                         class="inspira-input" 
                         required />
                </div>
              </div>
              <div class="md:col-span-2">
                <label for="message" class="block text-gray-700 mb-2 font-medium">Mensaje</label>
                <div class="relative">
                  <textarea id="message" v-model="contactForm.message" rows="5" 
                            class="inspira-input" 
                            required></textarea>
                </div>
              </div>
              <div class="md:col-span-2 flex flex-col sm:flex-row gap-4">
                <button type="submit" class="inspira-button primary">
                  <span class="flex items-center justify-center">
                    <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-send mr-2"><path d="m22 2-7 20-4-9-9-4Z"/><path d="M22 2 11 13"/></svg>
                    Enviar mensaje
                  </span>
                </button>
                <a href="https://wa.me/1234567890" target="_blank" class="inspira-button whatsapp">
                  <span class="flex items-center justify-center">
                    <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-message-circle mr-2"><path d="M7.9 20A9 9 0 1 0 4 16.1L2 22Z"/></svg>
                    Contactar por WhatsApp
                  </span>
                </a>
              </div>
            </form>
          </div>
        </div>
      </section>
</template>
<script setup>

// Contact form
const contactForm = ref({
  name: '',
  email: '',
  message: ''
});

// Form submission
const submitForm = () => {
  // Here you would typically send the form data to your backend
  alert('¡Formulario enviado! Nos pondremos en contacto contigo pronto.');
  // Reset form
  contactForm.value = {
    name: '',
    email: '',
    message: ''
  };
};

</script>