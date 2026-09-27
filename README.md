# 🚀 SAVIO — Tu Copiloto Financiero Personal (Fintech App)

¡Bienvenido al repositorio de presentación de **SAVIO**! Esta es una aplicación web premium de finanzas personales y gestión patrimonial orientada al mercado español. 

A diferencia de los clonadores de gastos tradicionales, SAVIO actúa como un ecosistema inteligente que analiza de forma integral la salud financiera del usuario, automatiza presupuestos adaptativos, evalúa perfiles inversores con rigor analítico y ofrece asistencia personalizada mediante Inteligencia Artificial.

*Nota: Actualmente el proyecto se encuentra en fase **BETA**. Este repositorio público funciona como un escaparate de portafolio técnico y de producto para describir su arquitectura funcional, manteniendo el código fuente protegido de forma privada.*

## 🔗 Enlace al Sitio de Demostración (Demo en Vivo)
Puedes acceder a la plataforma web en fase Beta, interactuar con los simuladores financieros y explorar su interfaz optimizada desde aquí:

👉 **[Visitar la Demo de SAVIO en Vivo](https://savioweb.base44.app)** *(Nota: Durante la Beta, las funciones PLUS están desbloqueadas y la pasarela de Stripe está configurada en modo sandbox/prueba sin cargos reales).*

---

## 💎 Identidad Visual y UI/UX Premium
La interfaz se ha diseñado bajo los más estrictos estándares del sector Fintech global:
* **Paleta de Colores:** Identidad corporativa de alta fidelidad basada en *Navy Blue* (`#0B1F3A`), *Orange/Gold* (`#F5A623`), blancos limpios y grises suaves.
* **Diseño UI:** Estética moderna, limpia y minimalista. Estructura basada en *cards* redondeadas con sombras sutiles.
* **Enfoque UX:** Diseño *Responsive* e interfaz nativa bajo filosofía **Mobile-First**, asegurando una experiencia fluida desde cualquier dispositivo móvil o de escritorio.

---

## 🧠 Arquitectura Funcional y Módulos Avanzados

### 1. Motor de Ingresos y Normalización Salarial
* Soporte para múltiples esquemas de cobro en España (mensual, quincenal, variable, y estructuras desde 12 hasta 15 pagas).
* Implementación de una **lógica de salario normalizado** centralizada que actúa como la fuente única de verdad para el resto de motores de la app.

### 2. Presupuesto Personalizado (Budget Engine Adaptativo)
* **`src/lib/budgetEngine.js`**: En lugar de aplicar la regla genérica 50/30/20, SAVIO procesa un cuestionario inicial detallado (vivienda, alimentación, deudas, transporte y prioridades financieras) guardado en `FinancialProfile`.
* El motor calcula un presupuesto adaptativo y dinámico determinando cuánto flujo de caja exacto puede destinar el usuario a cada área según su perfil.

### 3. Planificador de Objetivos y Fondo de Emergencia
* Sistema predictivo de metas financieras a corto, medio y largo plazo utilizando funciones de cálculo temporal optimizadas (`monthsUntil()`).
* El **Fondo de Emergencia** se autoajusta de manera inteligente basándose exclusivamente en los gastos esenciales reales calculados para el perfil de usuario.

### 4. Control de Patrimonio Neto (Net Worth Tracking)
* Consolidación de balances en tiempo real mediante el cálculo clásico de `Activos (Assets) - Pasivos (Liabilities)`.
* Incorporación de una lógica avanzada de migración (`NetWorthSnapshot`) que integra las carteras de inversión como activos sin incurrir en doble contabilidad.

### 5. Simuladores Financieros Centralizados
* **`src/lib/simulators.js`**: Núcleo matemático reutilizable y optimizado que centraliza fórmulas financieras críticas para evitar duplicidad de lógica (`calculateFutureValue`, `calculateCompoundGrowth`, `yearlyEvolution`, etc.).

### 6. Módulo de Inversiones y Perfilado del Inversor
* Gestión de carteras (`Investment`): Trackeo por tipo de activo, plataforma, ISIN/ticker, coste medio e importes con cálculo automatizado de rentabilidades en `src/lib/investments.js`.
* **InvestorProfile**: Evaluación bidimensional rigurosa que separa la **tolerancia psicológica al riesgo** de la **capacidad financiera real para soportar pérdidas**, midiendo además conocimientos, horizontes y necesidades de liquidez.

### 7. Motor de Emparejamiento (Investment Research & Matching)
* **`src/lib/investmentMatching.js`**: Motor educativo de recomendación y análisis que cruza los productos financieros reales disponibles (fondos, ETFs, depósitos, cuentas remuneradas) con el perfil del usuario.
* El matching no es arbitrario; evalúa de forma transparente criterios de costes (TER), fiscalidad en España, horizontes mínimos, diversificación y riesgo.

### 8. SAVIO IA — Asistente Financiero Contextual
* `/savio-ia`: Integración de un copiloto basado en IA con **acceso contextual ciego al estado financiero actual del usuario** (presupuestos, gastos, patrimonio). Es capaz de desglosar, explicar y sugerir optimizaciones financieras en lenguaje natural.

---

## 🛠️ Stack Tecnológico y Despliegue
* **Infraestructura:** Desarrollado, gestionado e integrado nativamente dentro del entorno de desarrollo de **Base44**.
* **Frontend:** Single Page Application (SPA) construida con **React y JavaScript** respetando los estándares de rendimiento del ecosistema de origen.
* **Control de Versiones:** Repositorio enlazado directamente a GitHub como entorno central de referencia para el despliegue continuo de código.

---

*Nota de Privacidad: El código fuente y la propiedad intelectual de la lógica algorítmica de SAVIO se encuentran protegidos en un repositorio privado propiedad del desarrollador. Para consultas técnicas o de arquitectura de software, contactar vía GitHub.*
