#  HexGuardTool

**HexGuardTool** es una herramienta modular de **auditoría y hardening para sistemas Linux** que permite fortalecer automáticamente la seguridad, detectar configuraciones inseguras y aplicar correcciones prácticas mediante 10 módulos especializados.  
Creado por **Lucas Román “LUCASFOKING”**.  
Repositorio: [https://github.com/LUCAS-ROMAN-VELASQUEZ/HexguardTool](https://github.com/LUCAS-ROMAN-VELASQUEZ/HexguardTool)

---

##  Descripción

HexGuardTool automatiza tareas de seguridad en servidores y máquinas Linux (Debian/Ubuntu/Kali/Parrot). Integra múltiples controles de seguridad en un solo script Python, ideal para administradores, estudiantes o entornos de práctica.

---

## Características principales

HexGuardTool agrupa **10 módulos de seguridad independientes**, que pueden ejecutarse individualmente o en conjunto:

| Módulo | Función |
|--------|---------|
| **MOD‑01 – Actualización del Sistema** | Actualiza paquetes, aplica parches y elimina dependencias huérfanas. |
| **MOD‑02 – Firewall UFW** | Configura un firewall restrictivo (deny-all entrante) con excepciones para SSH/HTTP/HTTPS. |
| **MOD‑03 – SSH Hardening** | Protege SSH: deshabilita login root y autenticación por contraseña. |
| **MOD‑04 – Fail2Ban** | Instala y configura Fail2Ban para mitigar ataques de fuerza bruta. |
| **MOD‑05 – Escaneo de Rootkits** | Ejecuta chkrootkit para detectar rootkits y backdoors. |
| **MOD‑06 – Auditoría de Usuarios** | Lista cuentas, detecta UID 0 y muestra últimos logins. |
| **MOD‑07 – Servicios Inseguros** | Deshabilita servicios que transmiten datos en texto plano. |
| **MOD‑08 – Permisos Críticos** | Corrige permisos de archivos esenciales (/etc/passwd, shadow, root, sudoers). |
| **MOD‑09 – Análisis de Logs SSH** | Analiza intentos fallidos y top IPs atacantes. |
| **MOD‑10 – Hardening Completo** | Ejecuta todos los módulos en orden seguro. |

---

##  Requisitos

-  **Python 3.8+**  
-  **Permisos de superusuario (root)**  
-  Sistema Linux compatible: Debian / Ubuntu / Kali / Parrot

---

##  Instalación

Clona el repositorio y prepara el script:

```bash
git clone https://github.com/LUCAS-ROMAN-VELASQUEZ/HexguardTool.git
cd HexguardTool
chmod +x hexguard.py
```
Verifica la instalación:

```bash
sudo python3 hexguard.py --version
 Uso
 Modo interactivo
sudo python3 hexguard.py
```
Aparece un menú para ejecutar cualquier módulo de forma interactiva.

Ejecutar un módulo específico
```bashsudo python3 hexguard.py --update         # Actualización del sistema
sudo python3 hexguard.py --firewall       # Firewall
sudo python3 hexguard.py --ssh            # SSH Hardening
 Hardening completo
sudo python3 hexguard.py --full
```
 Otros flags

```bash
--no-banner → Ejecutar sin banner

--help → Mostrar ayuda completa
```

Ejemplo de ejecución
```bash
[+] Iniciando HexGuard…
[MOD‑01] Actualizando sistema… ✔ Sistema actualizado
[MOD‑02] Configurando firewall… ✔ UFW configurado
[MOD‑03] Hardening SSH… ✔ Acceso root deshabilitado
...
[✔] Sistema securizado correctamente
```
Advertencias

Uso exclusivo en sistemas autorizados

 SSH Hardening: asegúrate de tener configurada una llave pública antes de ejecutar

Hardening completo: ten acceso físico o consola de emergencia para revertir cambios si algo falla

Restaurar configuraciones (ejemplo SSH)
```bash
sudo cp /etc/ssh/sshd_config.bak /etc/ssh/sshd_config
sudo systemctl restart ssh
```
Buenas prácticas

Revisa los logs en /var/log/hexguard.log

Ejecuta módulos individuales antes de aplicar hardening completo

Combina HexGuardTool con otras auditorías de seguridad

Autor y Licencia

Autor: Lucas Román “LUCASFOKING”
📄 Licencia: MIT — Open Source

Futuras mejoras

Interfaz gráfica (GUI)

Reportes exportables

Integración con sistemas SIEM

Soporte para más distros Linux
