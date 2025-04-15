<template>
  <div class="min-h-screen flex flex-col overflow-hidden bg-gradient-to-b from-[#f8fafc] to-[#f0f7ff]">
    <!-- Elementos decorativos de fondo -->
    <div class="inspira-bg">
      <div class="blob blob-1"></div>
      <div class="blob blob-2"></div>
      <div class="blob blob-3"></div>
      <div class="noise-overlay"></div>
    </div>
    <Header />
    <SectionsHero />
    <SectionsServicios />
    <SectionsBeneficios  />
    <SectionsProceso/>
    <SectionsTestimonios />
    <SectionsContact />
    <Footer />
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

// Mobile menu state
const mobileMenuOpen = ref(false);
const scrolled = ref(false);


// Scroll handler for header effect
const handleScroll = () => {
  scrolled.value = window.scrollY > 50;
};

// Lifecycle hooks
onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>



<style>
/* Inspira UI Styles */

/* Base Styles */
:root {
  --primary-gradient: linear-gradient(135deg, #007BFF, #00C896);
  --secondary-gradient: linear-gradient(135deg, #f0f7ff, #e6fffa);
  --primary-color: #007BFF;
  --secondary-color: #00C896;
  --accent-color: #FF6B6B;
  --text-color: #2D3748;
  --light-text: #718096;
  --background: #f8fafc;
  --card-bg: #ffffff;
  --shadow-sm: 0 4px 6px -1px rgba(0, 0, 0, 0.05), 0 2px 4px -1px rgba(0, 0, 0, 0.03);
  --shadow-md: 0 10px 15px -3px rgba(0, 0, 0, 0.08), 0 4px 6px -2px rgba(0, 0, 0, 0.04);
  --shadow-lg: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
  --shadow-inner: inset 0 2px 4px 0 rgba(0, 0, 0, 0.06);
  --border-radius: 16px;
  --transition: all 0.3s ease;
}

/* Background Elements */
.inspira-bg {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 0;
  overflow: hidden;
  pointer-events: none;
}

.blob {
  position: absolute;
  border-radius: 50%;
  filter: blur(60px);
  opacity: 0.15;
  animation: float 20s infinite alternate ease-in-out;
}

.blob-1 {
  width: 600px;
  height: 600px;
  background: var(--primary-color);
  top: -200px;
  left: -200px;
}

.blob-2 {
  width: 500px;
  height: 500px;
  background: var(--secondary-color);
  bottom: -100px;
  right: -100px;
  animation-delay: 5s;
}

.blob-3 {
  width: 300px;
  height: 300px;
  background: var(--accent-color);
  top: 40%;
  left: 60%;
  animation-delay: 10s;
}

.noise-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.65' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noiseFilter)'/%3E%3C/svg%3E");
  opacity: 0.03;
  mix-blend-mode: overlay;
}

/* Buttons */
.inspira-button {
  position: relative;
  padding: 0.75rem 1.5rem;
  border-radius: 12px;
  font-weight: 600;
  transition: var(--transition);
  overflow: hidden;
  cursor: pointer;
  display: inline-flex;
  align-items: center;
  justify-content: center;
}

.inspira-button.primary {
  background: var(--primary-gradient);
  color: white;
  box-shadow: 0 10px 20px -10px rgba(0, 123, 255, 0.5);
}

.inspira-button.primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 14px 28px -10px rgba(0, 123, 255, 0.6);
}

.inspira-button.secondary {
  background: white;
  color: var(--text-color);
  border: 1px solid rgba(0, 0, 0, 0.1);
  box-shadow: var(--shadow-sm);
}

.inspira-button.secondary:hover {
  transform: translateY(-3px);
  box-shadow: var(--shadow-md);
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

/* Cards */
.inspira-card {
  background: var(--card-bg);
  border-radius: var(--border-radius);
  padding: 2rem;
  transition: var(--transition);
  position: relative;
  overflow: hidden;
  box-shadow: var(--shadow-sm);
  border: 1px solid rgba(0, 0, 0, 0.05);
}

.inspira-card:hover {
  transform: translateY(-5px);
  box-shadow: var(--shadow-md);
  border-color: rgba(0, 123, 255, 0.2);
}

.inspira-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 4px;
  background: var(--primary-gradient);
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 0.5s ease;
}

.inspira-card:hover::before {
  transform: scaleX(1);
}

/* Icon Containers */
.inspira-icon-container {
  width: 60px;
  height: 60px;
  border-radius: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1.5rem;
  position: relative;
  color: white;
  background: var(--primary-gradient);
  box-shadow: 0 10px 20px -10px rgba(0, 123, 255, 0.3);
  transition: var(--transition);
}

.inspira-card:hover .inspira-icon-container {
  transform: scale(1.1) rotate(5deg);
}

.icon-1 { background: linear-gradient(135deg, #007BFF, #00C896); }
.icon-2 { background: linear-gradient(135deg, #00C896, #6366F1); }
.icon-3 { background: linear-gradient(135deg, #6366F1, #F43F5E); }
.icon-4 { background: linear-gradient(135deg, #F43F5E, #F97316); }
.icon-5 { background: linear-gradient(135deg, #F97316, #007BFF); }

/* Benefit Cards */
.inspira-benefit-card {
  background: var(--card-bg);
  border-radius: var(--border-radius);
  padding: 2rem;
  transition: var(--transition);
  position: relative;
  box-shadow: var(--shadow-sm);
  border: 1px solid rgba(0, 0, 0, 0.05);
  display: flex;
  flex-direction: column;
}

.inspira-benefit-card:hover {
  transform: translateY(-5px);
  box-shadow: var(--shadow-md);
}

.inspira-check-icon {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1rem;
  color: var(--primary-color);
  background: rgba(0, 123, 255, 0.1);
  transition: var(--transition);
}

.inspira-benefit-card:hover .inspira-check-icon {
  transform: rotate(360deg);
  background: var(--primary-color);
  color: white;
}

/* Process Cards */
.inspira-process-card {
  background: var(--card-bg);
  border-radius: var(--border-radius);
  padding: 2rem;
  transition: var(--transition);
  position: relative;
  box-shadow: var(--shadow-sm);
  border: 1px solid rgba(0, 0, 0, 0.05);
  z-index: 1;
}

.inspira-process-card:hover {
  transform: translateY(-5px);
  box-shadow: var(--shadow-md);
}

.inspira-process-number {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1rem;
  font-weight: bold;
  font-size: 1.25rem;
  color: white;
  background: var(--primary-gradient);
  box-shadow: 0 10px 20px -10px rgba(0, 123, 255, 0.3);
  transition: var(--transition);
}

.inspira-process-card:hover .inspira-process-number {
  transform: scale(1.1);
}

.inspira-process-line {
  position: absolute;
  top: 25%;
  left: 0;
  width: 100%;
  height: 2px;
  background: linear-gradient(90deg, rgba(0, 123, 255, 0.3), rgba(0, 200, 150, 0.3));
  z-index: 0;
  display: none;
}

@media (min-width: 1024px) {
  .inspira-process-line {
    display: block;
  }
}

/* Testimonial Cards */
.inspira-testimonial-card {
  background: var(--card-bg);
  border-radius: var(--border-radius);
  padding: 2rem;
  transition: var(--transition);
  position: relative;
  box-shadow: var(--shadow-sm);
  border: 1px solid rgba(0, 0, 0, 0.05);
}

.inspira-testimonial-card:hover {
  transform: translateY(-5px);
  box-shadow: var(--shadow-md);
}

.inspira-stars {
  display: flex;
  color: #FFD700;
  margin-bottom: 1rem;
}

.inspira-quote {
  font-style: italic;
  color: var(--light-text);
  margin-bottom: 1.5rem;
  font-size: 1.125rem;
  line-height: 1.6;
}

.inspira-avatar {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-right: 1rem;
  background: var(--primary-gradient);
  color: white;
}

/* Contact Form */
.inspira-contact-container {
  background: var(--card-bg);
  border-radius: var(--border-radius);
  padding: 2.5rem;
  box-shadow: var(--shadow-lg);
  border: 1px solid rgba(0, 0, 0, 0.05);
  max-width: 800px;
  margin: 0 auto;
  position: relative;
  overflow: hidden;
}



.inspira-input {
  width: 100%;
  padding: 0.75rem 1rem;
  border-radius: 12px;
  border: 1px solid rgba(0, 0, 0, 0.1);
  background: white;
  transition: var(--transition);
  font-size: 1rem;
  color: var(--text-color);
  box-shadow: var(--shadow-inner);
}

.inspira-input:focus {
  outline: none;
  border-color: var(--primary-color);
  box-shadow: 0 0 0 3px rgba(0, 123, 255, 0.1);
}

/* Footer Styles */
.inspira-footer-decoration {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: 
    radial-gradient(circle at 20% 30%, rgba(0, 123, 255, 0.1) 0%, transparent 20%),
    radial-gradient(circle at 80% 70%, rgba(0, 200, 150, 0.1) 0%, transparent 20%);
  opacity: 0.3;
}

.inspira-footer-link {
  color: #A0AEC0;
  transition: var(--transition);
  display: inline-flex;
  align-items: center;
}

.inspira-footer-link:hover {
  color: white;
  transform: translateX(5px);
}

.inspira-footer-link::before {
  content: '→';
  opacity: 0;
  margin-right: 0.5rem;
  transition: var(--transition);
  transform: translateX(-10px);
}

.inspira-footer-link:hover::before {
  opacity: 1;
  transform: translateX(0);
}

.inspira-contact-item {
  display: flex;
  align-items: center;
  color: #A0AEC0;
  transition: var(--transition);
}

.inspira-contact-item:hover {
  color: white;
  transform: translateX(5px);
}

.inspira-contact-icon {
  margin-right: 0.75rem;
  color: var(--primary-color);
}

/* Badge */
.inspira-badge {
  position: relative;
  overflow: hidden;
}

.inspira-badge::after {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: linear-gradient(
    to right,
    rgba(255, 255, 255, 0) 0%,
    rgba(255, 255, 255, 0.3) 50%,
    rgba(255, 255, 255, 0) 100%
  );
  transform: rotate(30deg);
  animation: shimmer 3s infinite;
}

/* Image Container */
.inspira-image-container {
  position: relative;
  border-radius: var(--border-radius);
  overflow: hidden;
  box-shadow: var(--shadow-lg);
  transition: var(--transition);
}

.inspira-image-container:hover {
  transform: translateY(-5px) rotate(1deg);
}

.inspira-image {
  width: 100%;
  height: auto;
  border-radius: var(--border-radius);
  transition: var(--transition);
  transform: scale(1);
}

.inspira-image-container:hover .inspira-image {
  transform: scale(1.05);
}

.inspira-image-decoration {
  position: absolute;
  top: -20px;
  right: -20px;
  width: 140px;
  height: 140px;
  border-radius: 50%;
  background: var(--primary-gradient);
  opacity: 0.1;
  z-index: -1;
}

/* Pattern Backgrounds */
.inspira-pattern {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: 
    radial-gradient(rgba(0, 123, 255, 0.1) 1px, transparent 1px),
    radial-gradient(rgba(0, 200, 150, 0.1) 1px, transparent 1px);
  background-size: 20px 20px;
  background-position: 0 0, 10px 10px;
  opacity: 0.5;
  pointer-events: none;
}

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

/* Animations */
@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-20px); }
}

@keyframes shimmer {
  0% { transform: translateX(-100%) rotate(30deg); }
  100% { transform: translateX(100%) rotate(30deg); }
}

/* Responsive Adjustments */
@media (max-width: 768px) {
  .inspira-card,
  .inspira-benefit-card,
  .inspira-process-card,
  .inspira-testimonial-card {
    padding: 1.5rem;
  }
  
  .inspira-contact-container {
    padding: 1.5rem;
  }
}
</style>