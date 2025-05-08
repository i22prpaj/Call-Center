# Call-Center Integration

## Descripción

Este repositorio proporciona una solución completamente gratuita para integrar un centro de atención telefónica en Odoo Community, empleando Asterisk como centralita VoIP y Docker para un despliegue ágil y reproducible.

## Características principales

* **Contenedores Docker**: Odoo 14 y Asterisk 20.Todo orquestado con Docker Compose.
* **FastAGI y AMI**: Sincronización bidireccional de llamadas entre Asterisk y Odoo.
* **PJSIP**: Gestión avanzada de agentes y proveedores VoIP externos.
* **Módulos Odoo**: Incluye `asterisk_click2dial` y `base_phone_popup`.
* **Monitorización en tiempo real**: Métricas de colas, duración de llamadas y tiempos de espera.

## Requisitos

* Docker ≥ 20.10 y Docker Compose ≥ 1.29
* Git y conexión a Internet activa
* Credenciales AMI/ARI y datos SIP de tu proveedor VoIP

## Instalación

1. **Clonar el repositorio**

   ```bash
   git clone https://github.com/tu-usuario/odoo-asterisk-callcenter.git
   cd odoo-asterisk-callcenter
   ```
2. **Configurar credenciales**
   Edita `docker-compose.yml` para incluir tus valores de base de datos, AMI y SIP.
3. **Arrancar el entorno**

   ```bash
   chmod +x odoo-uco.sh
   ./odoo-uco.sh
   ```

   *o bien*

   ```bash
   docker-compose up -d --build
   ```

## Uso

* Accede a la interfaz web de Odoo en `http://localhost:8069`.
* Credenciales por defecto: **admin / admin** (ajustables en `odoo.conf`).
* Activa el **Modo desarrollador** en Odoo y actualiza la lista de aplicaciones.
* Instala los módulos: **Asterisk Click2Dial** y **Base Phone Popup**.
* Configura en Odoo:

  1. **Telecomunicaciones → Servidores Asterisk**
  2. **Usuarios → Telecomunicaciones** (asignar extensiones SIP).

## Contribución

1. Haz **fork** del repositorio.
2. Crea una rama: `feature/tu-mejora`.
3. Realiza tus cambios, confirma y sube la rama.
4. Abre un **Pull Request** describiendo tu aporte.
5. Para incidencias, utiliza la sección *Issues* de GitHub.

## Licencia

Este proyecto está licenciado bajo **AGPL-3.0**. Consulta el archivo `LICENSE` para más detalles.
