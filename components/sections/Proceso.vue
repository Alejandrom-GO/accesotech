<template>
  <section id="proceso" class="py-24 relative overflow-hidden">
    <!-- Fondo tecnológico con partículas y código -->
    <div class="tech-particles"></div>
    <div class="tech-code-bg"></div>
    
    <div class="container mx-auto px-4 relative z-10">
      <div class="text-center mb-16">
        <div class="tech-badge mb-6 inline-flex items-center px-4 py-2 rounded-full bg-gradient-to-r from-[#007BFF]/10 to-[#00C896]/10 text-[#007BFF] font-medium">
          <span class="mr-2 bg-gradient-to-r from-[#007BFF] to-[#00C896] w-3 h-3 rounded-full pulse-dot"></span>
          <span class="tech-badge-text">Metodología de desarrollo</span>
        </div>
        <h2 class="text-4xl font-bold text-gray-800 mb-4">¿Cómo trabajamos?</h2>
        <p class="text-xl text-gray-600 max-w-3xl mx-auto">
          Nuestro proceso de desarrollo está diseñado para maximizar la eficiencia y transparencia, 
          permitiéndote ver el progreso en tiempo real mientras construimos tu solución tecnológica.
        </p>
      </div>
      
      <!-- Timeline de proceso tecnológico -->
      <div class="tech-timeline-container">
        <!-- Línea central de la timeline -->
        <div class="tech-timeline-line">
          <div class="tech-timeline-progress" :style="{ height: timelineProgress + '%' }"></div>
        </div>
        
        <!-- Pasos del proceso en formato timeline -->
        <div class="tech-timeline-steps">
          <div v-for="(paso, index) in proceso" :key="index" 
               class="tech-timeline-step"
               :class="{'active': activeStep === index, 'right-aligned': index % 2 !== 0}"
               @mouseenter="activeStep = index" 
               @mouseleave="activeStep = null">
            
            <!-- Marcador de la timeline -->
            <div class="tech-timeline-marker">
              <div class="tech-timeline-dot">
                <span>{{ index + 1 }}</span>
                <div class="tech-timeline-pulse"></div>
              </div>
              <div class="tech-timeline-connector"></div>
            </div>
            
            <!-- Tarjeta de contenido -->
            <div class="tech-timeline-card">
              <!-- Indicador de fase -->
              <div class="tech-phase-indicator">
                <div class="tech-phase-dot"></div>
                <span>{{ paso.fase }}</span>
              </div>
              
              <!-- Encabezado de la tarjeta -->
              <div class="tech-card-header">
                <div class="tech-step-icon">
                  <component :is="paso.icon" class="w-6 h-6" />
                </div>
                <div>
                  <h3 class="text-xl font-bold text-gray-800">{{ paso.title }}</h3>
                  <div class="tech-progress-bar">
                    <div class="tech-progress-fill" :style="{ width: paso.progreso + '%' }"></div>
                    <span class="tech-progress-text">{{ paso.progreso }}% del proceso</span>
                  </div>
                </div>
              </div>
              
              <!-- Contenido principal -->
              <div class="tech-card-content">
                <p class="text-gray-600 mb-4">{{ paso.description }}</p>
                
                <!-- Detalles técnicos expandibles -->
                <div class="tech-details-container">
                  <div class="tech-details-header" @click="toggleDetails(index)">
                    <span>Detalles técnicos</span>
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="tech-details-icon" :class="{'rotate': expandedDetails === index}">
                      <path d="m6 9 6 6 6-6"/>
                    </svg>
                  </div>
                  
                  <div class="tech-details-content" :class="{'expanded': expandedDetails === index}">
                    <div class="tech-detail-section">
                      <h4 class="tech-detail-title">
                        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                          <path d="M12 2v4M12 18v4M4.93 4.93l2.83 2.83M16.24 16.24l2.83 2.83M2 12h4M18 12h4M4.93 19.07l2.83-2.83M16.24 7.76l2.83-2.83"/>
                        </svg>
                        Lo que hacemos
                      </h4>
                      <ul class="tech-detail-list">
                        <li v-for="(item, i) in paso.hacemos" :key="i">
                          <div class="tech-detail-bullet"></div>
                          <span>{{ item }}</span>
                        </li>
                      </ul>
                    </div>
                    
                    <div class="tech-detail-section">
                      <h4 class="tech-detail-title">
                        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                          <path d="M14.7 6.3a1 1 0 0 0 0 1.4l1.6 1.6a1 1 0 0 0 1.4 0l3.77-3.77a6 6 0 0 1-7.94 7.94l-6.91 6.91a2.12 2.12 0 0 1-3-3l6.91-6.91a6 6 0 0 1 7.94-7.94l-3.76 3.76z"/>
                        </svg>
                        Herramientas utilizadas
                      </h4>
                      <div class="tech-tools-grid">
                        <div v-for="(tool, t) in paso.herramientas" :key="t" class="tech-tool">
                          {{ tool }}
                        </div>
                      </div>
                    </div>
                    
                    <div class="tech-detail-section">
                      <h4 class="tech-detail-title">
                        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                          <path d="M12 8v4l3 3"/>
                          <circle cx="12" cy="12" r="10"/>
                        </svg>
                        Duración y entregables
                      </h4>
                      <div class="tech-timeline-info">
                        <div class="tech-timeline-item">
                          <div class="tech-timeline-marker-small"></div>
                          <div class="tech-timeline-content">
                            <span class="tech-timeline-title">Duración:</span>
                            <span class="tech-timeline-text">{{ paso.tiempo }}</span>
                          </div>
                        </div>
                        <div class="tech-timeline-item">
                          <div class="tech-timeline-marker-small"></div>
                          <div class="tech-timeline-content">
                            <span class="tech-timeline-title">Entregables:</span>
                            <span class="tech-timeline-text">{{ paso.entregables }}</span>
                          </div>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
                
                <!-- Tu participación -->
                <div class="tech-participation">
                  <h4 class="tech-participation-title">
                    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                      <path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/>
                      <circle cx="9" cy="7" r="4"/>
                      <path d="M23 21v-2a4 4 0 0 0-3-3.87"/>
                      <path d="M16 3.13a4 4 0 0 1 0 7.75"/>
                    </svg>
                    Tu participación
                  </h4>
                  <p class="tech-participation-text">{{ paso.participacion }}</p>
                </div>
              </div>
              
              <!-- Código decorativo -->
              <div class="tech-code-snippet" v-if="paso.codigo">
                <div class="tech-code-header">
                  <span>{{ paso.codigo.lenguaje }}</span>
                  <div class="tech-code-dots">
                    <div class="tech-code-dot"></div>
                    <div class="tech-code-dot"></div>
                    <div class="tech-code-dot"></div>
                  </div>
                </div>
                <pre class="tech-code-content">{{ paso.codigo.snippet }}</pre>
              </div>
            </div>
          </div>
        </div>
        
        <!-- CTA tecnológico -->
        <div class="tech-cta">
          <div class="tech-cta-container">
            <div class="tech-cta-decoration"></div>
            <h3 class="text-2xl font-bold mb-4">¿Listo para iniciar tu proyecto tecnológico?</h3>
            <p class="text-gray-600 mb-6">Nuestro equipo está preparado para convertir tu idea en una solución digital de alto impacto.</p>
            <a href="#contacto" class="tech-button">
              <span class="tech-button-text">Iniciar proyecto</span>
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
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
import SvgSearch from '../svg/SvgSearch.vue';
import SvgLayout from '../svg/SvgLayout.vue';
import SvgCode from '../svg/SvgCode.vue';
import SvgRocket from '../svg/SvgRocket.vue';


// Estados para interactividad
const activeStep = ref(null);
const expandedDetails = ref(null);
const timelineProgress = ref(0);

// Función para expandir/contraer detalles
const toggleDetails = (index) => {
  if (expandedDetails.value === index) {
    expandedDetails.value = null;
  } else {
    expandedDetails.value = index;
  }
};

// Función para actualizar el progreso de la timeline basado en el scroll
const updateTimelineProgress = () => {
  const timelineElement = document.querySelector('.tech-timeline-container');
  if (!timelineElement) return;
  
  const rect = timelineElement.getBoundingClientRect();
  const windowHeight = window.innerHeight;
  
  // Calcular qué porcentaje de la timeline está visible
  const visiblePercentage = Math.min(
    Math.max(
      (windowHeight - rect.top) / (rect.height + windowHeight) * 100,
      0
    ),
    100
  );
  
  timelineProgress.value = visiblePercentage;
};

// Configurar y limpiar el evento de scroll
onMounted(() => {
  window.addEventListener('scroll', updateTimelineProgress);
  updateTimelineProgress();
});

onUnmounted(() => {
  window.removeEventListener('scroll', updateTimelineProgress);
});

// Datos del proceso con información técnica expandida
const proceso = [
  {
    title: 'Descubrimiento y análisis',
    description: 'Analizamos a fondo tus necesidades, objetivos de negocio y requerimientos técnicos para diseñar la solución óptima.',
    icon: SvgSearch,
    progreso: 25,
    fase: 'Fase de planificación',
    hacemos: [
      'Entrevistas con stakeholders clave',
      'Análisis de procesos actuales',
      'Identificación de puntos de dolor',
      'Definición de objetivos medibles',
      'Evaluación de sistemas existentes'
    ],
    herramientas: [
      'Miro', 'Figma', 'Notion', 'Draw.io', 'Google Analytics'
    ],
    tiempo: '1-2 semanas',
    entregables: 'Documento de requerimientos, mapa de procesos y propuesta técnica',
    participacion: 'Necesitaremos reuniones con tu equipo para entender a fondo tus necesidades y procesos actuales.',
    codigo: {
      lenguaje: 'JSON',
      snippet: '{\n  "proyecto": "Sistema de gestión",\n  "cliente": "Accesotech",\n  "objetivos": [\n    "Optimizar procesos",\n    "Reducir tiempos",\n    "Mejorar experiencia"\n  ],\n  "prioridad": "Alta"\n}'
    }
  },
  {
    title: 'Diseño y arquitectura',
    description: 'Creamos la arquitectura técnica y el diseño de interfaz que servirán como base para el desarrollo de tu solución.',
    icon: SvgLayout,
    progreso: 50,
    fase: 'Fase de diseño',
    hacemos: [
      'Diseño de arquitectura del sistema',
      'Modelado de base de datos',
      'Wireframes y prototipos interactivos',
      'Definición de APIs y servicios',
      'Planificación de seguridad y escalabilidad'
    ],
    herramientas: [
      'Figma', 'Adobe XD', 'AWS Architecture', 'MongoDB Atlas', 'Swagger'
    ],
    tiempo: '2-3 semanas',
    entregables: 'Prototipos interactivos, diagrama de arquitectura y modelo de datos',
    participacion: 'Revisarás y aprobarás los diseños y prototipos antes de pasar a la fase de desarrollo.',
    codigo: {
      lenguaje: 'SQL',
      snippet: 'CREATE TABLE usuarios (\n  id INT PRIMARY KEY,\n  nombre VARCHAR(100),\n  email VARCHAR(100),\n  rol VARCHAR(50),\n  fecha_registro TIMESTAMP\n);\n\nCREATE TABLE proyectos (\n  id INT PRIMARY KEY,\n  nombre VARCHAR(100),\n  cliente_id INT,\n  estado VARCHAR(50)\n);'
    }
  },
  {
    title: 'Desarrollo e implementación',
    description: 'Nuestro equipo construye tu solución utilizando metodologías ágiles, con entregas incrementales para validación continua.',
    icon: SvgCode,
    progreso: 75,
    fase: 'Fase de construcción',
    hacemos: [
      'Desarrollo frontend y backend',
      'Integración con sistemas externos',
      'Implementación de base de datos',
      'Testing automatizado',
      'Optimización de rendimiento'
    ],
    herramientas: [
      'React/Vue', 'Node.js', 'Flutter', 'GitHub', 'Docker', 'AWS/Azure'
    ],
    tiempo: '4-12 semanas',
    entregables: 'Código fuente, documentación técnica y versiones incrementales del producto',
    participacion: 'Tendrás acceso a versiones preliminares para probar funcionalidades y proporcionar feedback.',
    codigo: {
      lenguaje: 'JavaScript',
      snippet: 'async function fetchUserData() {\n  try {\n    const response = await api.get(\'/users\');\n    return response.data.map(user => ({\n      id: user.id,\n      name: user.name,\n      role: user.role,\n      active: user.status === \'active\'\n    }));\n  } catch (error) {\n    console.error(\'Error:\', error);\n    return [];\n  }\n}'
    }
  },
  {
    title: 'Lanzamiento y soporte',
    description: 'Desplegamos tu solución en producción y te acompañamos con soporte continuo, monitoreo y mejoras evolutivas.',
    icon: SvgRocket,
    progreso: 100,
    fase: 'Fase de operación',
    hacemos: [
      'Despliegue en producción',
      'Capacitación a usuarios',
      'Monitoreo de rendimiento',
      'Soporte técnico continuo',
      'Implementación de mejoras'
    ],
    herramientas: [
      'AWS CloudWatch', 'New Relic', 'Sentry', 'Jira Service Desk', 'Google Analytics'
    ],
    tiempo: 'Continuo',
    entregables: 'Sistema en producción, documentación de usuario y plan de soporte',
    participacion: 'Te capacitaremos en el uso del sistema y estaremos disponibles para resolver dudas y problemas.',
    codigo: {
      lenguaje: 'YAML',
      snippet: 'version: \'3\'\nservices:\n  app:\n    image: accesotech/app:latest\n    ports:\n      - "3000:3000"\n    environment:\n      - NODE_ENV=production\n      - DB_HOST=db\n    depends_on:\n      - db\n  db:\n    image: postgres:13\n    volumes:\n      - db-data:/var/lib/postgresql/data\nvolumes:\n  db-data:'
    }
  }
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

/* Contenedor de la timeline */
.tech-timeline-container {
  position: relative;
  padding: 2rem 0 0rem 2rem;
}

/* Línea central de la timeline */
.tech-timeline-line {
  position: absolute;
  top: 0;
  left: 51%;
  width: 4px;
  height: 100%;
  background: rgba(0, 123, 255, 0.1);
  transform: translateX(-50%);
  overflow: hidden;
}

.tech-timeline-progress {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  background: linear-gradient(to top, #007BFF, #00C896);
  transition: height 0.5s ease;
}

/* Pasos de la timeline */
.tech-timeline-steps {
  position: relative;
  z-index: 1;
}

/* Paso individual de la timeline */
.tech-timeline-step {
  position: relative;
  margin-bottom: 6rem;
  display: flex;
  align-items: center;
  justify-content:start;
}

.tech-timeline-step:last-child {
  margin-bottom: 0;
}

/* Alineación alternada de los pasos */
.tech-timeline-step {
  padding-right: 50%;
}

.tech-timeline-step.right-aligned {
  padding-right: 0;
  padding-left: 50%;
  flex-direction: row-reverse;
  justify-content: end;
}

/* Marcador de la timeline */
.tech-timeline-marker {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  z-index: 2;
}

/* Punto de la timeline */
.tech-timeline-dot {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background: linear-gradient(135deg, #007BFF, #00C896);
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-weight: bold;
  font-size: 1.1rem;
  box-shadow: 0 10px 20px -5px rgba(0, 123, 255, 0.4);
  position: relative;
  z-index: 2;
  transition: all 0.3s ease;
}

.tech-timeline-step.active .tech-timeline-dot {
  transform: scale(1.1);
  box-shadow: 0 15px 30px -5px rgba(0, 123, 255, 0.5);
}

/* Pulso del punto */
.tech-timeline-pulse {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background: linear-gradient(135deg, #007BFF, #00C896);
  opacity: 0;
  z-index: -1;
  animation: pulse-animation 2s infinite;
}

.tech-timeline-step.active .tech-timeline-pulse {
  opacity: 0.3;
}

@keyframes pulse-animation {
  0% {
    transform: scale(1);
    opacity: 0.3;
  }
  50% {
    transform: scale(1.3);
    opacity: 0;
  }
  100% {
    transform: scale(1);
    opacity: 0;
  }
}

/* Conector de la timeline */
.tech-timeline-connector {
  width: 50px;
  height: 40px;
  margin-top: 10px;
}

/* Tarjeta de contenido */
.tech-timeline-card {
  width: 90%;
  background: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(10px);
  border-radius: 16px;
  border: 1px solid rgba(0, 123, 255, 0.1);
  box-shadow: 
    0 10px 25px -5px rgba(0, 0, 0, 0.1),
    0 0 15px rgba(0, 123, 255, 0.1);
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  position: relative;
  overflow: hidden;
  margin-left: 2rem;
  padding: 1rem;
}

.tech-timeline-step.right-aligned .tech-timeline-card {
  margin-left: 0;
  margin-right: 2rem;
}

.tech-timeline-step.active .tech-timeline-card {
  transform: translateY(-5px) scale(1.02);
  box-shadow: 
    0 20px 30px -10px rgba(0, 0, 0, 0.15),
    0 0 20px rgba(0, 123, 255, 0.2);
  border-color: rgba(0, 123, 255, 0.3);
}

/* Indicador de fase */
.tech-phase-indicator {
  position: absolute;
  top: 1rem;
  right: 1rem;
  display: flex;
  align-items: center;
  padding: 0.5rem 0.75rem;
  background: rgba(0, 123, 255, 0.05);
  border-radius: 20px;
  font-size: 0.75rem;
  color: #007BFF;
  font-weight: 500;
  z-index: 2;
}

.tech-phase-dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: linear-gradient(135deg, #007BFF, #00C896);
  margin-right: 0.5rem;
  animation: blink 1.5s infinite;
}

@keyframes blink {
  0% { opacity: 0.5; }
  50% { opacity: 1; }
  100% { opacity: 0.5; }
}

/* Encabezado de la tarjeta */
.tech-card-header {
  display: flex;
  align-items: center;
  padding: 1.5rem;
  border-bottom: 1px solid rgba(0, 123, 255, 0.1);
}

.tech-step-icon {
  width: 50px;
  height: 50px;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  background: linear-gradient(135deg, #007BFF, #00C896);
  box-shadow: 0 10px 15px -5px rgba(0, 123, 255, 0.3);
  margin-right: 1rem;
  flex-shrink: 0;
  transition: all 0.3s ease;
}

.tech-timeline-step.active .tech-step-icon {
  transform: rotate(10deg) scale(1.1);
}

/* Barra de progreso */
.tech-progress-bar {
  height: 6px;
  background: rgba(0, 0, 0, 0.05);
  border-radius: 3px;
  overflow: hidden;
  margin-top: 0.5rem;
  width: 100%;
  max-width: 200px;
}

.tech-progress-fill {
  height: 100%;
  background: linear-gradient(90deg, #007BFF, #00C896);
  border-radius: 3px;
  transition: width 1s ease;
}

.tech-progress-text {
  font-size: 0.75rem;
  color: #718096;
  font-weight: 500;
  display: block;
  margin-top: 0.25rem;
}

/* Contenido principal */
.tech-card-content {
  padding: 1.5rem;
}

/* Contenedor de detalles técnicos */
.tech-details-container {
  margin-top: 1.5rem;
  border-radius: 12px;
  border: 1px solid rgba(0, 123, 255, 0.1);
  overflow: hidden;
  transition: all 0.3s ease;
}

.tech-details-header {
  padding: 1rem;
  background: rgba(0, 123, 255, 0.05);
  display: flex;
  justify-content: space-between;
  align-items: center;
  cursor: pointer;
  font-weight: 600;
  color: #007BFF;
  transition: all 0.3s ease;
}

.tech-details-icon {
  transition: transform 0.3s ease;
}

.tech-details-icon.rotate {
  transform: rotate(180deg);
}

/* Contenido de detalles expandible */
.tech-details-content {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.5s ease;
}

.tech-details-content.expanded {
  max-height: 1000px;
}

/* Secciones de detalles */
.tech-detail-section {
  padding: 1rem;
  border-bottom: 1px solid rgba(0, 123, 255, 0.1);
}

.tech-detail-section:last-child {
  border-bottom: none;
}

.tech-detail-title {
  display: flex;
  align-items: center;
  font-weight: 600;
  color: #2D3748;
  margin-bottom: 1rem;
}

.tech-detail-title svg {
  margin-right: 0.5rem;
  color: #007BFF;
}

/* Lista de detalles */
.tech-detail-list {
  margin-left: 0.5rem;
}

.tech-detail-list li {
  display: flex;
  align-items: flex-start;
  margin-bottom: 0.5rem;
  font-size: 0.9rem;
}

.tech-detail-bullet {
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: linear-gradient(135deg, #007BFF, #00C896);
  margin-right: 0.75rem;
  margin-top: 0.5rem;
  flex-shrink: 0;
}

/* Grid de herramientas */
.tech-tools-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
  gap: 0.5rem;
}

.tech-tool {
  padding: 0.5rem;
  background: rgba(0, 123, 255, 0.05);
  border-radius: 6px;
  font-size: 0.8rem;
  text-align: center;
  color: #4A5568;
  border: 1px solid rgba(0, 123, 255, 0.1);
}

/* Línea de tiempo interna */
.tech-timeline-info {
  margin-top: 0.5rem;
}

.tech-timeline-item {
  display: flex;
  align-items: flex-start;
  margin-bottom: 0.75rem;
}

.tech-timeline-marker-small {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background: linear-gradient(135deg, #007BFF, #00C896);
  margin-right: 0.75rem;
  margin-top: 0.25rem;
  flex-shrink: 0;
}

.tech-timeline-content {
  flex-grow: 1;
}

.tech-timeline-title {
  font-weight: 600;
  color: #4A5568;
  margin-right: 0.5rem;
}

.tech-timeline-text {
  color: #718096;
}

/* Sección de participación */
.tech-participation {
  margin-top: 1.5rem;
  padding: 1rem;
  background: rgba(0, 200, 150, 0.05);
  border-radius: 12px;
  border-left: 3px solid rgba(0, 200, 150, 0.3);
}

.tech-participation-title {
  display: flex;
  align-items: center;
  font-weight: 600;
  color: #2D3748;
  margin-bottom: 0.5rem;
}

.tech-participation-title svg {
  margin-right: 0.5rem;
  color: #00C896;
}

.tech-participation-text {
  font-size: 0.9rem;
  color: #4A5568;
}

/* Fragmento de código */
.tech-code-snippet {
  margin-top: 1.5rem;
  border-radius: 12px;
  overflow: hidden;
  background: #1E293B;
  border: 1px solid rgba(0, 123, 255, 0.1);
}

.tech-code-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.75rem 1rem;
  background: #0F172A;
  color: #94A3B8;
  font-size: 0.85rem;
  font-family: monospace;
}

.tech-code-dots {
  display: flex;
  align-items: center;
}

.tech-code-dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  margin-left: 0.5rem;
}

.tech-code-dot:nth-child(1) {
  background: #EF4444;
}

.tech-code-dot:nth-child(2) {
  background: #F59E0B;
}

.tech-code-dot:nth-child(3) {
  background: #10B981;
}

.tech-code-content {
  padding: 1rem;
  color: #E2E8F0;
  font-family: monospace;
  font-size: 0.85rem;
  line-height: 1.5;
  overflow-x: auto;
  max-height: 380px;
}

/* CTA tecnológico */
.tech-cta {
  margin-top: 12rem;
  position: relative;
  z-index: 2;
}

.tech-cta-container {
  background: white;
  border-radius: 16px;
  padding: 2.5rem;
  box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
  border: 1px solid rgba(0, 123, 255, 0.1);
  position: relative;
  overflow: hidden;
  text-align: center;
  max-width: 800px;
  margin: 0 auto;
}

.tech-cta-decoration {
  position: absolute;
  top: -50px;
  right: -50px;
  width: 200px;
  height: 200px;
  border-radius: 50%;
  background: linear-gradient(135deg, rgba(0, 123, 255, 0.1), rgba(0, 200, 150, 0.1));
  z-index: 0;
}

/* Botón tecnológico */
.tech-button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 0.75rem 1.5rem;
  background: linear-gradient(135deg, #007BFF, #00C896);
  color: white;
  border-radius: 12px;
  font-weight: 600;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
  box-shadow: 0 10px 20px -10px rgba(0, 123, 255, 0.5);
}

.tech-button:hover {
  transform: translateY(-3px);
  box-shadow: 0 15px 25px -10px rgba(0, 123, 255, 0.6);
}

.tech-button-text {
  position: relative;
  z-index: 2;
  margin-right: 0.5rem;
}

.tech-button-icon {
  position: relative;
  z-index: 2;
  transition: transform 0.3s ease;
}

.tech-button:hover .tech-button-icon {
  transform: translateX(3px);
}

.tech-button-effect {
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
  transition: left 0.7s ease;
}

.tech-button:hover .tech-button-effect {
  left: 100%;
}

/* Responsive */
@media (max-width: 1023px) {
  .tech-timeline-line {
    left: 30px;
  }
  
  .tech-timeline-step {
    padding-left: 80px;
    padding-right: 0;
    flex-direction: row;
  }
  
  .tech-timeline-step.right-aligned {
    padding-left: 80px;
    padding-right: 0;
    flex-direction: row;
  }
  
  .tech-timeline-marker {
    left: 30px;
  }
  
  .tech-timeline-card {
    width: 100%;
    margin-left: 1rem;
  }
  
  .tech-timeline-step.right-aligned .tech-timeline-card {
    margin-left: 1rem;
    margin-right: 0;
  }
}

@media (max-width: 639px) {
  .tech-card-header {
    flex-direction: column;
    align-items: flex-start;
  }
  
  .tech-step-icon {
    margin-bottom: 1rem;
  }
}
</style>