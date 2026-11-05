# Pet Market Club - Backend API & CMS

Repositorio del backend para la plataforma de e-commerce **Pet Market Club**. 

Este proyecto funciona como un Headless CMS y una API RESTful desarrollada con **Strapi** (Node.js) y **PostgreSQL**. Centraliza toda la lógica de negocio, la persistencia de datos, la gestión de inventario y la comunicación segura con pasarelas de pago de terceros.

## Arquitectura y Lógica de Negocio (Core Features)
- **Trazabilidad de Inventario:** Implementación de controladores personalizados para evitar la mutación manual del stock. Las existencias solo se modifican mediante registros de ingreso (facturas) o extracciones justificadas.
- **Lógica de Combos Dinámicos:** Endpoints adaptados para calcular la disponibilidad en tiempo real de kits de productos basándose en el inventario de sus componentes individuales.
- **Integración de Pagos:** Conexión con el SDK de Mercado Pago, incluyendo la gestión de *Webhooks* para actualizar automáticamente el estado de los pedidos tras la confirmación del cobro.
- **Automatización de Comprobantes:** Generación de recibos en formato PDF (RF-12) y envío transaccional de correos electrónicos al confirmar órdenes o disparar alertas de reposición de stock.

## 🛠️ Stack Tecnológico
- **Framework:** Strapi v4 (Node.js)
- **Base de Datos:** PostgreSQL
- **Integraciones:** Mercado Pago SDK
- **Utilidades:** Generación de PDF (pdfkit/puppeteer) y servicio de Email (Resend/SendGrid).

## Instalación y Desarrollo Local
```bash
# Clonar el repositorio
git clone [https://github.com/tu-usuario/pet-market-api.git](https://github.com/tu-usuario/pet-market-api.git)

# Instalar dependencias
npm install

# Configurar variables de entorno
# Crear archivo .env basado en .env.example (Credenciales DB, API Keys Mercado Pago)

# Iniciar servidor en modo desarrollo
npm run develop
