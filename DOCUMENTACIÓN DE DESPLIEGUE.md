DOCUMENTACIÓN DE DESPLIEGUE - PROYECTO GEARX (ECOMMERCE)
Este documento detalla los requisitos y pasos necesarios para la migración y despliegue del proyecto al entorno de producción/empresa.

1. Servicios y Requisitos del Sistema
Para el correcto funcionamiento del contenedor, se deben asegurar los siguientes servicios:

Servidor Web: Apache2 con el módulo mod_rewrite habilitado (vital para el manejo de enlaces permanentes y SEO).

Motor de Base de Datos: MariaDB o MySQL.

Lenguaje: PHP 8.x con las siguientes extensiones instaladas y activas:

curl, mbstring, xml, mysqli, gd, zip (requeridas por WooCommerce, Elementor y Starter Templates).

2. Archivos y Repositorio
Código Fuente: Se entrega el comprimido wordpress.zip que debe ser extraído en la ruta raíz del servidor (ej. /var/www/html/).

Base de Datos: Se adjunta el archivo wordpress.sql con la estructura y datos finales.

3. Pasos para la Restauración
Base de Datos: Crear una base de datos vacía e importar el archivo .sql vía phpMyAdmin o línea de comandos.

Configuración: Actualizar el archivo wp-config.php con las nuevas credenciales de la base de datos (DB_NAME, DB_USER, DB_PASSWORD).

Permisos: Asegurar permisos de escritura en la carpeta wp-content/uploads para permitir la subida de medios.

Enlaces Permanentes: Una vez desplegado, acceder al administrador y en Ajustes > Enlaces permanentes, hacer clic en "Guardar cambios" para regenerar el archivo .htaccess.

4. Ajustes de Dominio/IP (Search & Replace)
Nota Técnica: Las URLs internas están configuradas actualmente con la IP local de desarrollo http://192.168.1.11.

Se requiere realizar un Search and Replace en la base de datos hacia el nuevo dominio/IP o actualizar los campos siteurl y home en la tabla wp_options.

5. Integraciones y Herramientas Implementadas
E-commerce: WooCommerce con Astra Theme y Elementor.

SEO: Configuración completa con Yoast SEO (títulos y meta descripciones optimizadas).

Analítica: Integración de Google Tag Manager (ID: GTM-WCBDVJ9S) activa en el header y body.

Seguridad: Entorno preparado para migración a HTTPS. Se recomienda instalar el certificado SSL en el nuevo contenedor para activar el protocolo seguro.

6. Credenciales de Acceso
Administrador WordPress: * Usuario: admin

Contraseña: 02032007GPab!