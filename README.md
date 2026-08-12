# ecosistema-ia-atencion-cliente
Entrega final IA Automation
[Ver video de demostración en Google Drive](https://drive.google.com/file/d/1txXKaQhHRII13y8rc6UZxN88MSLBBEX6/view?usp=sharing)
🤖 Ecosistema de Automatización IA Autónomo para Negocios

> **Entrega Final - Arquitectura de Flujos de Automatización IA**

---

## 📌 Resumen del Proyecto
Sistema autónomo de atención al cliente y gestión de consultas vía Gmail, integrado con **n8n**, **OpenAI (GPT-4o-mini)**, **Airtable** como memoria central y un punto de validación humana **Human-in-the-Loop (HITL)** para evitar envíos no autorizados.

---

## 🔗 Enlaces Obligatorios de la Entrega

* 📹 **Video Demostrativo de Funcionamiento (Drive):** [Ver Video en Google Drive]
* 📊 **Dashboard de Control & Base de Datos (Shared View):** [Ver Vista Pública de Airtable/Notion](https://airtable.com/invite/l?inviteId=invcSbHxxUYfBLltH&inviteToken=fcb2fb942b209ba2ee3d2d7f73c9c1d3359c2c842d78cb02e881f51c4116c3fe&utm_medium=email&utm_source=product_team&utm_content=transactional-alerts)
* 📄 **Documentación Técnica Oficial (PDF):** [Descargar PDF Técnico]
* ⚙️ **Workflow exportado (JSON):** [Ver Archivo JSON]

---

## ⚙️ Resumen de los 5 Criterios de Evaluación

### 1. Mapa de Arquitectura 
* **Trigger:** Gmail Trigger (con filtro de exclusión de bucles `-from:brigatosantiago@gmail.com`).
* **Base de Datos:** Airtable (registro y estado).
* **IA:** AI Agent + OpenAI Chat Model (`GPT-4o-mini`).
* **HITL:** Nodo `Send and Wait` por correo electrónico.
* **Salida:** `Reply to a message` en el hilo de conversación.
* **Resiliencia:** Rutas mediante `Error Trigger` para fallos de API.
* 
### 2. Estructura de Datos
* Tablas vinculadas de `Clientes` e `Interacciones`.
* Estados del flujo: `Pendiente`, `Procesado_IA`, `En_Aprobacion`, `Aprobado`, `Error`.

### 3. Matriz de Optimización de Costos 
* **GPT-4o-mini:** Utilizado para clasificación y redacción estándar (Ahorro del 92% respecto a modelos flagship).
* **Claude 3.5 Sonnet:** Reservado para RAG y lectura densa de adjuntos.
* **Batch API:** Para análisis masivos no en tiempo real.

### 4. Seguridad, Resiliencia y HITL
* Encapsulamiento de credenciales sin variables hardcodeadas.
* Control estricto antes del envío final mediante HITL para mitigar alucinaciones.
* Captura de excepciones con `Error Trigger`.

### 5. Dashboard de Control 
* Vista pública de métricas con KPIs de volumen, tiempo de respuesta, % de aprobación y tasa de errores.

---

## 📸 Evidencias de Ejecución
*(Las capturas se encuentran disponibles en la carpeta `/evidencias` del repositorio)*
