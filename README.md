# Call-Center Integration

## Descripción

Este repositorio proporciona una solución completamente gratuita para integrar un centro de atención telefónica en Odoo Community, empleando Asterisk como centralita VoIP y Docker para un despliegue ágil y reproducible.

## Características principales

* **Contenedores Docker**: Odoo 14 y Asterisk 20.11.0 .Todo orquestado con Docker Compose.
* **FastAGI, AMI y ARI**: Sincronización bidireccional de llamadas entre Asterisk y Odoo.
* **PJSIP**: Gestión avanzada de agentes y proveedores VoIP externos.
* **Módulos Odoo**: Incluye `asterisk_click2dial` , `base_phone` y `connector-telephony-14.0`.
* **Monitorización en tiempo real**: Métricas de colas, duración de llamadas y tiempos de espera.

## Requisitos

* Docker ≥ 20.10 y Docker Compose ≥ 1.29
* Git y conexión a Internet activa
* Credenciales AMI/ARI y datos SIP de tu proveedor VoIP

## Instalación

1. **Clonar el repositorio**

   ```bash
   git clone https://github.com/i22prpaj/Call-Center.git
   cd Call-Center/call_center-odoo
   ```
2. **Configurar credenciales**
   Edita `docker-compose.yml` para incluir tus valores de base de datos, AMI y SIP.
3. **Arrancar el entorno**

   ```bash
   chmod u+x odoo-uco.sh
   ./odoo-uco.sh -start
   ```

   *o bien*

   ```bash
   sudo apt install docker-compose
   cd config
   docker-compose -f docker-compose.yml up -d
   ```

## Uso

* Accede a la interfaz web de Odoo en `http://localhost:8069`.
* Credenciales por defecto: **admin / admin** (ajustables en fichero`.env`).
* Activa el **Modo desarrollador** en Odoo y actualiza la lista de aplicaciones.
* Instala los módulos: **Asterisk Click2Dial** y **Base Phone**.
* Configura en Odoo:

  1. **Technical → Asterisk servers**
  2. **Users & Companies → Users → Telephony** (asignar extensiones SIP).

## Contribución

1. Haz **fork** del repositorio.
2. Crea una rama: `feature/tu-mejora`.
3. Realiza tus cambios, confirma y sube la rama.
4. Abre un **Pull Request** describiendo tu aporte.
5. Para incidencias, utiliza la sección *Issues* de GitHub.

## Licencia

Este proyecto está licenciado bajo **AGPL-3.0**. Consulta el archivo `LICENSE` para más detalles.
