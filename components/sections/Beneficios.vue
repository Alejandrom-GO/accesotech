<template>
        <!-- Beneficios Section -->
        <section id="beneficios" class="py-24 relative overflow-hidden">
            <div class="inspira-pattern"></div>
            <div class="container mx-auto px-4 relative z-10">
                  <div class="text-center mb-16">
                    <div class="tech-badge mb-6 inline-flex items-center px-4 py-2 rounded-full bg-gradient-to-r from-[#007BFF]/10 to-[#00C896]/10 text-[#007BFF] font-medium">
                      <span class="mr-2 bg-gradient-to-r from-[#007BFF] to-[#00C896] w-3 h-3 rounded-full pulse-dot"></span>
                      <span class="tech-badge-text">Nuestras ventajas</span>
                    </div>
                    <h2 class="text-5xl font-bold text-gray-800 mb-4">¿Por qué elegir Accesotech?</h2>
                    <p class="text-xl text-gray-600 max-w-3xl mx-auto">
                      Combinamos experiencia técnica, metodologías ágiles y un enfoque centrado en resultados para ofrecer soluciones tecnológicas que generan valor real.
                    </p>
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
        <section id="ventajas" class="relative overflow-hidden">
            <!-- Fondo tecnológico con partículas y código -->
            <div class="tech-particles"></div>
            <div class="tech-code-bg"></div>
            <div class="container mx-auto px-4 relative z-10">
              <!-- CTA tecnológico -->
              <div class="tech-cta-2">
                <div class="tech-cta-container">
                  <div class="tech-cta-decoration"></div>
                  <h3 class="text-2xl font-bold mb-4">¿Listo para trabajar con expertos?</h3>
                  <p class="text-gray-600 mb-6">Nuestro equipo está preparado para ayudarte a alcanzar tus objetivos tecnológicos.</p>
                  <a href="#contacto" class="tech-button">
                    <span class="tech-button-text">Contáctanos</span>
                    <span class="tech-button-icon">
                      <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <path d="M5 12h14"/>
                        <path d="m12 5 7 7-7 7"/>
                      </svg>
                    </span>
                    <span class="tech-button-effect"></span>
                  </a>
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

// Estados para interactividad
const activeAdvantage = ref(null);

// Función para obtener iniciales
const getInitials = (name) => {
  return name
    .split(' ')
    .map(word => word[0])
    .join('')
    .toUpperCase()
    .substring(0, 2);
};

// Datos de ventajas
const ventajas = [
  {
    titulo: 'Equipo especializado',
    descripcion: 'Contamos con profesionales altamente cualificados en diferentes áreas de la tecnología, con experiencia en proyectos de diversos sectores y complejidad.',
    icon: 'svg-users'
  },
  {
    titulo: 'Metodología ágil',
    descripcion: 'Trabajamos con metodologías ágiles que permiten entregas incrementales, adaptación a cambios y una comunicación constante durante todo el proyecto.',
    icon: 'svg-git-branch'
  },
  {
    titulo: 'Soluciones a medida',
    descripcion: 'Desarrollamos soluciones personalizadas que se adaptan perfectamente a tus necesidades específicas, no utilizamos plantillas ni soluciones genéricas.',
    icon: 'svg-settings'
  },
  {
    titulo: 'Tecnología de vanguardia',
    descripcion: 'Utilizamos las tecnologías más avanzadas y mejores prácticas del mercado para garantizar soluciones robustas, escalables y preparadas para el futuro.',
    icon: 'svg-zap'
  },
  {
    titulo: 'Soporte continuo',
    descripcion: 'Ofrecemos acompañamiento y soporte técnico continuo después de la implementación para asegurar el óptimo funcionamiento de tu solución.',
    icon: 'svg-life-buoy'
  },
  {
    titulo: 'Resultados medibles',
    descripcion: 'Nos enfocamos en generar valor real para tu negocio con soluciones que impactan positivamente en tus indicadores clave de rendimiento.',
    icon: 'svg-bar-chart'
  }
];

// Datos de métricas
const metricas = [
  {
    etiqueta: 'Proyectos entregados a tiempo',
    valor: '98%',
    porcentaje: 98
  },
  {
    etiqueta: 'Satisfacción de clientes',
    valor: '96%',
    porcentaje: 96
  },
  {
    etiqueta: 'Reducción de costos operativos',
    valor: '45%',
    porcentaje: 45
  },
  {
    etiqueta: 'Mejora en eficiencia de procesos',
    valor: '67%',
    porcentaje: 67
  },
  {
    etiqueta: 'Tasa de retención de clientes',
    valor: '92%',
    porcentaje: 92
  }
];

// Datos de testimonios
const testimonios = [
  {
    texto: 'Accesotech transformó completamente nuestros procesos internos con una solución tecnológica que superó todas nuestras expectativas. Su enfoque ágil y la calidad del trabajo fueron excepcionales.',
    autor: 'María Rodríguez',
    cargo: 'CTO, Empresa de Logística'
  },
  {
    texto: 'La aplicación móvil desarrollada por Accesotech nos permitió aumentar nuestras ventas en un 35% en solo tres meses. Su equipo entendió perfectamente nuestras necesidades y entregó un producto de alta calidad.',
    autor: 'Carlos Méndez',
    cargo: 'Director de Marketing, Retail'
  },
  {
    texto: 'La consultoría tecnológica de Accesotech nos ayudó a identificar oportunidades de mejora que no habíamos considerado. Su roadmap tecnológico ha sido nuestra guía para la transformación digital.',
    autor: 'Laura Sánchez',
    cargo: 'CEO, Startup Fintech'
  }
];

// Datos de certificaciones
const certificaciones = [
  {
    nombre: 'AWS Partner',
    icon: 'svg-cloud'
  },
  {
    nombre: 'Microsoft Gold',
    icon: 'svg-window'
  },
  {
    nombre: 'Google Cloud',
    icon: 'svg-server'
  },
  {
    nombre: 'ISO 27001',
    icon: 'svg-shield'
  },
  {
    nombre: 'CMMI Nivel 4',
    icon: 'svg-award'
  },
  {
    nombre: 'Agile Certified',
    icon: 'svg-check-circle'
  }
];

// Datos de tecnologías
const tecnologias = [
  { nombre: 'React', tamaño: 1.4 },
  { nombre: 'Vue.js', tamaño: 1.6 },
  { nombre: 'Angular', tamaño: 1.3 },
  { nombre: 'Node.js', tamaño: 1.7 },
  { nombre: 'Python', tamaño: 1.5 },
  { nombre: 'Django', tamaño: 1.2 },
  { nombre: 'Laravel', tamaño: 1.4 },
  { nombre: 'AWS', tamaño: 1.8 },
  { nombre: 'Docker', tamaño: 1.5 },
  { nombre: 'Kubernetes', tamaño: 1.3 },
  { nombre: 'MongoDB', tamaño: 1.4 },
  { nombre: 'PostgreSQL', tamaño: 1.6 },
  { nombre: 'TensorFlow', tamaño: 1.3 },
  { nombre: 'Flutter', tamaño: 1.5 },
  { nombre: 'React Native', tamaño: 1.4 },
  { nombre: 'GraphQL', tamaño: 1.2 },
  { nombre: 'TypeScript', tamaño: 1.6 },
  { nombre: 'Swift', tamaño: 1.3 },
  { nombre: 'Kotlin', tamaño: 1.4 },
  { nombre: 'Firebase', tamaño: 1.5 }
];


</script>

<style>
/* Fondos tecnológicos */
.tech-particles {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: 
    radial-gradient(rgba(0, 123, 255, 0.1) 1px, transparent 1px),
    radial-gradient(rgba(0, 200, 150, 0.05) 1px, transparent 1px);
  background-size: 20px 20px, 30px 30px;
  background-position: 0 0, 15px 15px;
  opacity: 0.5;
  pointer-events: none;
}

.tech-code-bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  opacity: 0.03;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='400' height='400' viewBox='0 0 800 800'%3E%3Cg fill='none' stroke='%23007BFF' stroke-width='1'%3E%3Cpath d='M769 229L1037 260.9M927 880L731 737 520 660 309 538 40 599 295 764 126.5 879.5 40 599-197 493 102 382-31 229 126.5 79.5-69-63'/%3E%3Cpath d='M-31 229L237 261 390 382 603 493 308.5 537.5 101.5 381.5M370 905L295 764'/%3E%3Cpath d='M520 660L578 842 731 737 840 599 603 493 520 660 295 764 309 538 390 382 539 269 769 229 577.5 41.5 370 105 295 -36 126.5 79.5 237 261 102 382 40 599 -69 737 127 880'/%3E%3Cpath d='M520-140L578.5 42.5 731-63M603 493L539 269 237 261 370 105M902 382L539 269M390 382L102 382'/%3E%3Cpath d='M-222 42L126.5 79.5 370 105 539 269 577.5 41.5 927 80 769 229 902 382 603 493 731 737M295-36L577.5 41.5M578 842L295 764M40-201L127 80M102 382L-261 269'/%3E%3C/g%3E%3Cg fill='%2300C896'%3E%3Ccircle cx='769' cy='229' r='5'/%3E%3Ccircle cx='539' cy='269' r='5'/%3E%3Ccircle cx='603' cy='493' r='5'/%3E%3Ccircle cx='731' cy='737' r='5'/%3E%3Ccircle cx='520' cy='660' r='5'/%3E%3Ccircle cx='309' cy='538' r='5'/%3E%3Ccircle cx='295' cy='764' r='5'/%3E%3Ccircle cx='40' cy='599' r='5'/%3E%3Ccircle cx='102' cy='382' r='5'/%3E%3Ccircle cx='127' cy='80' r='5'/%3E%3Ccircle cx='370' cy='105' r='5'/%3E%3Ccircle cx='578' cy='42' r='5'/%3E%3Ccircle cx='237' cy='261' r='5'/%3E%3Ccircle cx='390' cy='382' r='5'/%3E%3C/g%3E%3C/svg%3E");
  pointer-events: none;
}

/* Badge tecnológico */
.tech-badge {
  transition: all 0.3s ease;
  border: 1px solid rgba(0, 123, 255, 0.2);
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
  backdrop-filter: blur(8px);
}

.tech-badge:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
}

.tech-badge-text {
  background: linear-gradient(90deg, #007BFF, #00C896);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  font-weight: 600;
}

.pulse-dot {
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0% { transform: scale(1); opacity: 1; }
  50% { transform: scale(1.5); opacity: 0.5; }
  100% { transform: scale(1); opacity: 1; }
}

/* Contenedor de ventajas */
.tech-advantages-container {
  display: grid;
  grid-template-columns: 1fr;
  gap: 3rem;
}

/* Grid de ventajas */
.tech-advantages-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.5rem;
}

/* Tarjeta de ventaja */
.tech-advantage-card {
  position: relative;
  background: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(10px);
  border-radius: 16px;
  border: 1px solid rgba(0, 123, 255, 0.1);
  padding: 2rem;
  box-shadow: 
    0 10px 25px -5px rgba(0, 0, 0, 0.1),
    0 0 15px rgba(0, 123, 255, 0.1);
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  overflow: hidden;
}

.tech-advantage-card.active {
  transform: translateY(-5px);
  box-shadow: 
    0 20px 30px -10px rgba(0, 0, 0, 0.15),
    0 0 20px rgba(0, 123, 255, 0.2);
  border-color: rgba(0, 123, 255, 0.3);
}

.tech-advantage-icon {
  width: 60px;
  height: 60px;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  background: linear-gradient(135deg, #007BFF, #00C896);
 }
 </style>