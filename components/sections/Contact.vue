<template>
  <section id="contacto" class="py-24 relative overflow-hidden">
    <div class="inspira-dots"></div>
    <div class="container mx-auto px-4 relative z-10">
      <div class="text-center mb-16">
        <h2 class="text-4xl font-bold text-gray-800 mb-4">¿Tienes una idea o necesitas una solución para tu negocio?</h2>
        <p class="text-xl text-gray-600 max-w-2xl mx-auto">Hablemos. Estamos listos para ayudarte.</p>
      </div>
      
      <div class="flex flex-col lg:flex-row gap-12 items-center">
        <!-- Columna izquierda - Llamado a la acción -->
        <div class="lg:w-2/5">
          <div class="inspira-cta-container">
            <div class="inspira-cta-decoration"></div>
            <div class="relative z-10">
              <h3 class="text-3xl font-bold mb-6 text-transparent bg-clip-text bg-gradient-to-r from-[#007BFF] to-[#00C896]">
                Transforma tu negocio con tecnología a tu medida
              </h3>
              
              <p class="text-lg text-gray-600 mb-8">
                Cada proyecto es único y merece soluciones personalizadas. Nuestro equipo está listo para convertir tus ideas en realidad.
              </p>
              
              <div class="space-y-4">
                <div class="inspira-cta-feature">
                  <div class="inspira-cta-icon">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-zap"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"/></svg>
                  </div>
                  <div>
                    <h4 class="font-bold text-gray-800">Respuesta rápida</h4>
                    <p class="text-gray-600">Te contactamos en menos de 24 horas</p>
                  </div>
                </div>
                
                <div class="inspira-cta-feature">
                  <div class="inspira-cta-icon">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-shield-check"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10"/><path d="m9 12 2 2 4-4"/></svg>
                  </div>
                  <div>
                    <h4 class="font-bold text-gray-800">Sin compromisos</h4>
                    <p class="text-gray-600">Consulta inicial gratuita y sin obligaciones</p>
                  </div>
                </div>
                
                <div class="inspira-cta-feature">
                  <div class="inspira-cta-icon">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-users"><path d="M16 21v-2a4 4 0 0 0-4-4H6a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M22 21v-2a4 4 0 0 0-3-3.87"/><path d="M16 3.13a4 4 0 0 1 0 7.75"/></svg>
                  </div>
                  <div>
                    <h4 class="font-bold text-gray-800">Equipo especializado</h4>
                    <p class="text-gray-600">Profesionales con experiencia en tu industria</p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        
        <!-- Columna derecha - Formulario de contacto -->
        <div class="lg:w-3/5">
          <div class="inspira-contact-container">
            <div class="inspira-contact-decoration"></div>
            
            <form @submit.prevent="submitForm" class="relative z-10" v-if="!formSubmitted">
              <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <div class="inspira-form-group">
                  <div class="inspira-input-wrapper">
                    <input 
                      type="text" 
                      id="name" 
                      v-model="contactForm.name" 
                      class="inspira-input-field" 
                      :class="{'has-value': contactForm.name}" 
                      required 
                    />
                    <label for="name" class="inspira-input-label">Nombre</label>
                    <div class="inspira-input-line"></div>
                    <div class="inspira-input-icon">
                      <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-user"><path d="M19 21v-2a4 4 0 0 0-4-4H9a4 4 0 0 0-4 4v2"/><circle cx="12" cy="7" r="4"/></svg>
                    </div>
                  </div>
                </div>
                
                <div class="inspira-form-group">
                  <div class="inspira-input-wrapper">
                    <input 
                      type="email" 
                      id="email" 
                      v-model="contactForm.email" 
                      class="inspira-input-field" 
                      :class="{'has-value': contactForm.email}" 
                      required 
                    />
                    <label for="email" class="inspira-input-label">Email</label>
                    <div class="inspira-input-line"></div>
                    <div class="inspira-input-icon">
                      <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-mail"><rect width="20" height="16" x="2" y="4" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
                    </div>
                  </div>
                </div>
                
                <div class="inspira-form-group md:col-span-2">
                  <div class="inspira-input-wrapper">
                    <input 
                      type="tel" 
                      id="phone" 
                      v-model="contactForm.phone" 
                      class="inspira-input-field" 
                      :class="{'has-value': contactForm.phone}" 
                    />
                    <label for="phone" class="inspira-input-label">Teléfono (opcional)</label>
                    <div class="inspira-input-line"></div>
                    <div class="inspira-input-icon">
                      <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-phone"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"/></svg>
                    </div>
                  </div>
                </div>
                
                <div class="inspira-form-group md:col-span-2">
                  <div class="inspira-select-wrapper">
                    <select 
                      id="service" 
                      v-model="contactForm.service" 
                      class="inspira-select-field" 
                      :class="{'has-value': contactForm.service}" 
                      required
                    >
                      <option value="" disabled selected></option>
                      <option value="app">Desarrollo de aplicaciones móviles</option>
                      <option value="web">Plataformas web personalizadas</option>
                      <option value="system">Sistemas internos de gestión</option>
                      <option value="website">Sitios web profesionales</option>
                      <option value="integration">Integraciones con herramientas externas</option>
                    </select>
                    <label for="service" class="inspira-input-label">Servicio que te interesa</label>
                    <div class="inspira-input-line"></div>
                    <div class="inspira-input-icon">
                      <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-briefcase"><rect width="20" height="14" x="2" y="7" rx="2" ry="2"/><path d="M16 21V5a2 2 0 0 0-2-2h-4a2 2 0 0 0-2 2v16"/></svg>
                    </div>
                  </div>
                </div>
                
                <div class="inspira-form-group md:col-span-2">
                  <div class="inspira-textarea-wrapper">
                    <textarea 
                      id="message" 
                      v-model="contactForm.message" 
                      rows="4" 
                      class="inspira-textarea-field" 
                      :class="{'has-value': contactForm.message}" 
                      required
                    ></textarea>
                    <label for="message" class="inspira-textarea-label">Cuéntanos sobre tu proyecto</label>
                    <div class="inspira-input-line"></div>
                    <div class="inspira-input-icon">
                      <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-message-square"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>
                    </div>
                  </div>
                </div>
              </div>
              
              <div class="inspira-form-footer">
                <div class="inspira-privacy-notice">
                  <input type="checkbox" id="privacy" v-model="contactForm.privacy" required class="inspira-checkbox" />
                  <label for="privacy" class="inspira-checkbox-label">
                    Acepto la <a href="#" class="inspira-link">política de privacidad</a> y el tratamiento de mis datos
                  </label>
                </div>
                
                <div class="flex flex-col sm:flex-row gap-4 mt-8">
                  <button type="submit" class="inspira-button primary">
                    <span class="flex items-center justify-center">
                      <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-send mr-2"><path d="m22 2-7 20-4-9-9-4Z"/><path d="M22 2 11 13"/></svg>
                      Enviar mensaje
                    </span>
                    <span class="inspira-button-effect"></span>
                  </button>
                  <a href="https://wa.me/1234567890" target="_blank" class="inspira-button whatsapp">
                    <span class="flex items-center justify-center">
                      <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-message-circle mr-2"><path d="M7.9 20A9 9 0 1 0 4 16.1L2 22Z"/></svg>
                      Contactar por WhatsApp
                    </span>
                    <span class="inspira-button-effect"></span>
                  </a>
                </div>
              </div>
            </form>
            
            <div class="inspira-form-success" v-if="formSubmitted">
              <div class="inspira-success-icon">
                <svg xmlns="http://www.w3.org/2000/svg" width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-check-circle"><path d="M22 11.08V12a10 10 0 1 1-5.93-9.14"/><path d="m9 11 3 3L22 4"/></svg>
              </div>
              <h3 class="text-2xl font-bold text-gray-800 mb-2">¡Mensaje enviado!</h3>
              <p class="text-gray-600">Nos pondremos en contacto contigo pronto.</p>
              <button @click="resetForm" class="inspira-button secondary mt-6">
                <span>Enviar otro mensaje</span>
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';

// Contact form
const contactForm = ref({
  name: '',
  email: '',
  phone: '',
  service: '',
  message: '',
  privacy: false
});

// Form submission state
const formSubmitted = ref(false);

// Form submission
const submitForm = () => {
  // Here you would typically send the form data to your backend
  console.log('Form submitted:', contactForm.value);
  
  // Show success message
  formSubmitted.value = true;
};

// Reset form
const resetForm = () => {
  contactForm.value = {
    name: '',
    email: '',
    phone: '',
    service: '',
    message: '',
    privacy: false
  };
  formSubmitted.value = false;
};
</script>

<style>
/* Dots background */
.inspira-dots {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: 
    radial-gradient(rgba(0, 123, 255, 0.1) 1px, transparent 1px);
  background-size: 20px 20px;
  opacity: 0.5;
  pointer-events: none;
}

/* Contact container */
.inspira-contact-container {
  background: white;
  border-radius: 24px;
  padding: 2.5rem;
  box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
  border: 1px solid rgba(0, 0, 0, 0.05);
  position: relative;
  overflow: hidden;
  height: 100%;
}

.inspira-contact-decoration {
  position: absolute;
  top: -100px;
  right: -100px;
  width: 300px;
  height: 300px;
  border-radius: 50%;
  background: linear-gradient(135deg, rgba(0, 123, 255, 0.1), rgba(0, 200, 150, 0.1));
  z-index: 0;
}

/* CTA Container */
.inspira-cta-container {
  background: white;
  border-radius: 24px;
  padding: 2.5rem;
  box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
  border: 1px solid rgba(0, 0, 0, 0.05);
  position: relative;
  overflow: hidden;
  height: 100%;
}

.inspira-cta-decoration {
  position: absolute;
  top: -50px;
  left: -50px;
  width: 200px;
  height: 200px;
  border-radius: 50%;
  background: linear-gradient(135deg, rgba(0, 123, 255, 0.1), rgba(0, 200, 150, 0.1));
  z-index: 0;
}

/* CTA Features */
.inspira-cta-feature {
  display: flex;
  align-items: center;
  margin-bottom: 1rem;
  padding: 1rem;
  border-radius: 12px;
  background: rgba(0, 123, 255, 0.03);
  transition: all 0.3s ease;
}

.inspira-cta-feature:hover {
  background: rgba(0, 123, 255, 0.08);
  transform: translateX(5px);
}

.inspira-cta-icon {
  width: 40px;
  height: 40px;
  border-radius: 10px;
  background: linear-gradient(135deg, #007BFF, #00C896);
  display: flex;
  align-items: center;
  justify-content: center;
  margin-right: 1rem;
  color: white;
  flex-shrink: 0;
}

/* Form groups */
.inspira-form-group {
  position: relative;
  margin-bottom: 1rem;
}

/* Input wrappers */
.inspira-input-wrapper,
.inspira-textarea-wrapper,
.inspira-select-wrapper {
  position: relative;
}

/* Input fields */
.inspira-input-field,
.inspira-textarea-field,
.inspira-select-field {
  width: 100%;
  padding: 0.75rem 1rem 0.75rem 2.5rem;
  border: none;
  border-bottom: 1px solid rgba(0, 0, 0, 0.1);
  background: transparent;
  transition: all 0.3s ease;
  font-size: 1rem;
  color: #2D3748;
  position: relative;
  z-index: 1;
}

.inspira-textarea-field {
  resize: none;
  min-height: 120px;
}

.inspira-select-field {
  appearance: none;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24' fill='none' stroke='%23718096' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'%3E%3Cpath d='m6 9 6 6 6-6'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right 0.5rem center;
  background-size: 1.25rem;
}

/* Input focus and hover states */
.inspira-input-field:focus,
.inspira-textarea-field:focus,
.inspira-select-field:focus {
  outline: none;
  border-color: transparent;
}

/* Input labels */
.inspira-input-label,
.inspira-textarea-label {
  position: absolute;
  left: 2.5rem;
  top: 0.75rem;
  color: #718096;
  transition: all 0.3s ease;
  pointer-events: none;
  z-index: 0;
}

/* Label animation */
.inspira-input-field:focus ~ .inspira-input-label,
.inspira-textarea-field:focus ~ .inspira-textarea-label,
.inspira-select-field:focus ~ .inspira-input-label,
.inspira-input-field.has-value ~ .inspira-input-label,
.inspira-textarea-field.has-value ~ .inspira-textarea-label,
.inspira-select-field.has-value ~ .inspira-input-label {
  top: -0.5rem;
  left: 2.5rem;
  font-size: 0.75rem;
  color: #007BFF;
  font-weight: 600;
}

/* Input line animation */
.inspira-input-line {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background: linear-gradient(135deg, #007BFF, #00C896);
  transition: all 0.3s ease;
}

.inspira-input-field:focus ~ .inspira-input-line,
.inspira-textarea-field:focus ~ .inspira-input-line,
.inspira-select-field:focus ~ .inspira-input-line {
  width: 100%;
}

/* Input icons */
.inspira-input-icon {
  position: absolute;
  left: 0.5rem;
  top: 0.75rem;
  color: #718096;
  transition: all 0.3s ease;
}

.inspira-input-field:focus ~ .inspira-input-icon,
.inspira-textarea-field:focus ~ .inspira-input-icon,
.inspira-select-field:focus ~ .inspira-input-icon,
.inspira-input-field.has-value ~ .inspira-input-icon,
.inspira-textarea-field.has-value ~ .inspira-input-icon,
.inspira-select-field.has-value ~ .inspira-input-icon {
  color: #007BFF;
}

/* Form footer */
.inspira-form-footer {
  margin-top: 2rem;
}

/* Privacy notice */
.inspira-privacy-notice {
  display: flex;
  align-items: flex-start;
  margin-bottom: 1rem;
}

/* Custom checkbox */
.inspira-checkbox {
  position: absolute;
  opacity: 0;
  cursor: pointer;
  height: 0;
  width: 0;
}

.inspira-checkbox-label {
  position: relative;
  padding-left: 2rem;
  cursor: pointer;
  font-size: 0.875rem;
  color: #718096;
  user-select: none;
  display: inline-block;
}

.inspira-checkbox-label::before {
  content: '';
  position: absolute;
  left: 0;
  top: 0;
  width: 1.25rem;
  height: 1.25rem;
  border: 1px solid rgba(0, 0, 0, 0.1);
  border-radius: 4px;
  background-color: white;
  transition: all 0.3s ease;
}

.inspira-checkbox-label::after {
  content: '';
  position: absolute;
  left: 0.4rem;
  top: 0.25rem;
  width: 0.5rem;
  height: 0.75rem;
  border: solid white;
  border-width: 0 2px 2px 0;
  transform: rotate(45deg) scale(0);
  opacity: 0;
  transition: all 0.3s ease;
}

.inspira-checkbox:checked ~ .inspira-checkbox-label::before {
  background: linear-gradient(135deg, #007BFF, #00C896);
  border-color: transparent;
}

.inspira-checkbox:checked ~ .inspira-checkbox-label::after {
  transform: rotate(45deg) scale(1);
  opacity: 1;
}

/* Link styles */
.inspira-link {
  color: #007BFF;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
}

.inspira-link:hover {
  color: #00C896;
  text-decoration: underline;
}

/* Button effect */
.inspira-button-effect {
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
  transition: left 0.7s ease;
}

.inspira-button:hover .inspira-button-effect {
  left: 100%;
}

/* Success message */
.inspira-form-success {
  text-align: center;
  padding: 2rem;
}

.inspira-success-icon {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  background: linear-gradient(135deg, rgba(0, 123, 255, 0.1), rgba(0, 200, 150, 0.1));
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 1.5rem;
  color: #007BFF;
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.05); }
  100% { transform: scale(1); }
}

/* Buttons */
.inspira-button {
  position: relative;
  padding: 0.75rem 1.5rem;
  border-radius: 12px;
  font-weight: 600;
  transition: all 0.3s ease;
  overflow: hidden;
  cursor: pointer;
  display: inline-flex;
  align-items: center;
  justify-content: center;
}

.inspira-button.primary {
  background: linear-gradient(135deg, #007BFF, #00C896);
  color: white;
  box-shadow: 0 10px 20px -10px rgba(0, 123, 255, 0.5);
}

.inspira-button.primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 14px 28px -10px rgba(0, 123, 255, 0.6);
}

.inspira-button.secondary {
  background: white;
  color: #2D3748;
  border: 1px solid rgba(0, 0, 0, 0.1);
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05), 0 2px 4px -1px rgba(0, 0, 0, 0.03);
}

.inspira-button.secondary:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.08), 0 4px 6px -2px rgba(0, 0, 0, 0.04);
  border-color: rgba(0, 123, 255, 0.3);
}

.inspira-button.whatsapp {
  background: #25D366;
  color: white;
  box-shadow: 0 10px 20px -10px rgba(37, 211, 102, 0.5);
}

.inspira-button.whatsapp:hover {
  transform: translateY(-3px);
  box-shadow: 0 14px 28px -10px rgba(37, 211, 102, 0.6);
}

/* Responsive adjustments */
@media (max-width: 1023px) {
  .inspira-contact-container,
  .inspira-cta-container {
    padding: 2rem;
    margin-bottom: 2rem;
  }
}
</style>