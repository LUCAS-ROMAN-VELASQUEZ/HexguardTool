🛡️ HexGuardTool

HexGuardTool es una herramienta modular de auditoría y hardening para sistemas Linux que permite automáticamente fortalecer la seguridad, detectar configuraciones inseguras y aplicar correcciones prácticas con un conjunto de 10 módulos especializados.

📌 Descripción

HexGuardTool automatiza tareas comunes de seguridad en servidores y máquinas con Linux (especialmente Debian/Ubuntu/Kali/Parrot). Integra múltiples controles de seguridad en un solo script Python fácil de usar, ideal tanto para administradores como para estudiantes o entornos de práctica.

🚀 Características principales

HexGuardTool agrupa 10 módulos de seguridad independientes que pueden ejecutarse individualmente o en conjunto para aplicar configuraciones de hardening:

Módulo	Función
MOD‑01 – Actualización del Sistema	Actualiza paquetes, aplica parches y elimina dependencias huérfanas.
MOD‑02 – Firewall UFW	Configura firewall restrictivo (deny‑all entrante) con excepciones para SSH/HTTP/HTTPS.
MOD‑03 – SSH Hardening	Asegura SSH deshabilitando login root y autenticación por contraseña.
MOD‑04 – Fail2Ban	Instala y configura Fail2Ban para mitigar ataques de fuerza bruta.
MOD‑05 – Escaneo de Rootkits	Ejecuta chkrootkit para detectar rootkits y backdoors conocidos.
MOD‑06 – Auditoría de Usuarios	Lista cuentas, detecta UID 0 y muestra últimos logins.
MOD‑07 – Servicios Inseguros	Deshabilita servicios que transmiten datos en texto plano.
MOD‑08 – Permisos Críticos	Verifica y corrige permisos de archivos esenciales (/etc/passwd, shadow, root, sudoers).
MOD‑09 – Análisis de Logs SSH	Analiza intentos fallidos y las IPs más activas en auth.log.
MOD‑10 – Hardening Completo	Ejecuta todos los módulos de forma secuencial y ordenada.
📦 Requisitos

Antes de usar HexGuardTool:

🐍 Python 3.8+

🛠️ Permisos de superusuario (root)

💻 Sistema Linux compatible (Debian/Ubuntu/Kali/Parrot)

🚧 Instalación

Clona el repositorio y prepara el script:

git clone https://github.com/LUCAS-ROMAN-VELASQUEZ/HexguardTool.git
cd HexguardTool
chmod +x hexguard.py

Verifica la versión:

sudo python3 hexguard.py --version
⚙️ Uso
🧩 Modo interactivo

Ejecuta sin argumentos para ver un menú interactivo:

sudo python3 hexguard.py
🎯 Ejecutar un módulo específico
sudo python3 hexguard.py --update         # Solo actualización del sistema
sudo python3 hexguard.py --firewall       # Solo firewall
sudo python3 hexguard.py --ssh            # Solo hardening de SSH
🛠 Hardening completo
sudo python3 hexguard.py --full
📌 Otros flags útiles

--no-banner: Ejecutar sin mostrar el banner.

--help: Mostrar ayuda completa.

📋 Ejemplo de ejecución
[+] Iniciando HexGuard…
[MOD‑01] Actualizando sistema… ✔ Sistema actualizado
[MOD‑02] Configurando firewall… ✔ UFW configurado
[MOD‑03] Hardening SSH… ✔ Acceso root deshabilitado
…
[✔] Sistema securizado correctamente
⚠️ Advertencias

🔒 Uso exclusivo en sistemas autorizados
Modifica configuraciones críticas del sistema. Nunca lo ejecutes en sistemas ajenos sin permiso claro.

🔑 SSH Hardening
Antes de aplicar cambios de SSH, asegúrate de tener configurada una llave pública SSH para evitar quedarte sin acceso remoto.

📍 Hardening completo
Se recomienda tener acceso físico o consola de emergencia por si es necesario revertir cambios.

🔄 Restaurar configuraciones

Por ejemplo, para restaurar SSH en caso de error:

sudo cp /etc/ssh/sshd_config.bak /etc/ssh/sshd_config
sudo systemctl restart ssh
🧠 Buenas prácticas

✔ Revisa los logs generados en /var/log/hexguard.log para auditoría.
✔ Usa módulos individualmente antes de aplicar hardening completo.
✔ Combina HexGuardTool con análisis de seguridad adicionales (análisis de puertos, revisión de políticas de contraseñas, etc.).

🧑‍💻 Autor y Licencia

Autor: Lucas Román “LUCASFOKING”
📄 Licencia: MIT — Open Source

📈 Futuras mejoras (Opcionales)

Interfaz gráfica (GUI)

Reportes exportables

Integración con sistemas SIEM

Soporte para más distros Linux