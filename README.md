🛡️ HexGuard

“HexGuard automatiza la seguridad de Linux: detecta, corrige y blinda el sistema en minutos.”

📌 Descripción

HexGuard es una herramienta modular de auditoría y hardening para sistemas Linux, diseñada para aplicar medidas de seguridad reales de forma automatizada.

Permite analizar el estado del sistema, detectar configuraciones inseguras y aplicar correcciones mediante un conjunto de 10 módulos de seguridad, orientados a proteger accesos, servicios y archivos críticos.

Está pensada para:

Administradores de sistemas

Estudiantes de ciberseguridad

Laboratorios y entornos de práctica

⚙️ Características

🔄 Actualización automática del sistema

🔥 Configuración de firewall (UFW)

🔐 Hardening de SSH

🚫 Protección contra fuerza bruta (Fail2Ban)

🕵️ Detección de rootkits

👥 Auditoría de usuarios

⚠️ Detección de servicios inseguros

🔒 Corrección de permisos críticos

📊 Análisis de logs SSH

Ejecución completa automatizada

Módulos
Módulo	Descripción
MOD-01	Actualización del sistema
MOD-02	Configuración de firewall
MOD-03	Hardening de SSH
MOD-04	Fail2Ban
MOD-05	Escaneo de rootkits
MOD-06	Auditoría de usuarios
MOD-07	Servicios inseguros
MOD-08	Permisos críticos
MOD-09	Análisis de logs SSH
MOD-10	Hardening completo
Instalación
git clone https://github.com/tuusuario/hexguard.git
cd hexguard
chmod +x hexguard.sh
Uso

Ejecutar la herramienta:

sudo ./hexguard.sh

Ejecutar un módulo específico:

sudo ./hexguard.sh --mod 03

Ejecutar hardening completo:

sudo ./hexguard.sh --full
Ejemplo de ejecución
[+] Iniciando HexGuard...

[MOD-01] Actualizando sistema...
✔ Sistema actualizado correctamente

[MOD-02] Configurando firewall...
✔ UFW activo (SSH, HTTP, HTTPS permitidos)

[MOD-03] Hardening SSH...
✔ Acceso root deshabilitado
✔ Autenticación por clave habilitada

...

[✔] Sistema securizado correctamente
Evidencias

Incluye capturas o logs reales aquí, por ejemplo:

Configuración de UFW activa

Bloqueo de IPs con Fail2Ban

Resultados de escaneo de rootkits

Logs de intentos SSH

Controles de seguridad implementados

Gestión de actualizaciones y parches

Configuración de firewall restrictivo

Protección del acceso remoto (SSH)

Mitigación de ataques de fuerza bruta

Detección de malware y rootkits

Auditoría de cuentas y accesos

Eliminación de servicios inseguros

Protección de archivos críticos del sistema

Monitorización de intentos de acceso

Requisitos

Sistema Linux (Ubuntu/Debian recomendado)

Permisos de superusuario (root)

Conexión a Internet

Licencia

Este proyecto está bajo la licencia MIT.
Consulta el archivo LICENSE para más información.

Autor

LUCASFOKING

Mejoras futuras

Interfaz gráfica (GUI)

Exportación de reportes

Integración con SIEM

Soporte para más distribuciones Linux