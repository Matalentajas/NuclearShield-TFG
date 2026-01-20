# Playbook: Respuesta a Ransomware en Entorno OT (ICS)
**ID:** PB-01 | **Severidad:** CRÍTICA | **Ref:** NIST SP 800-61

## 1. Detección y Triaje
- [ ] **Alerta SIEM:** Cifrado masivo en Historian o tráfico C2 detectado[cite: 544].
- [ ] **Validación:** Descartar falsos positivos (actualizaciones, paradas programadas).
- [ ] **Declaración:** Activar Comité de Crisis si afecta a Nivel 3 (Supervisión).

## 2. Contención (Aislamiento)
> **PRIORIDAD:** Seguridad Física (Safety) del Reactor[cite: 535].
- [ ] **Corte IDMZ:** Aplicar regla "Deny All" en Firewall IT/OT (Aislamiento en isla)[cite: 554].
- [ ] **NO APAGAR:** Mantener equipos encendidos para preservar RAM (evidencia volátil)[cite: 560].
- [ ] **Desconexión:** Retirar cable de red (físico) o Shutdown Port en switch.

## 3. Análisis Forense
- [ ] **Volcado de Memoria:** Usar FTK Imager/Velociraptor en USB seguro[cite: 573].
- [ ] **Clonado de Disco:** Extraer discos y usar **Write Blockers** (Tableau) para imagen E01[cite: 578].
- [ ] **Cadena de Custodia:** Documentar Hash SHA-256.

## 4. Recuperación (Clean Room)
- [ ] **Backup Inmutable:** Acceder al repositorio Linux Hardened/WORM[cite: 589].
- [ ] **Staging:** Restaurar en entorno aislado ("Clean Room") sin red[cite: 590].
- [ ] **Escaneo Dual:** Analizar con 2 motores AV distintos antes de pasar a producción[cite: 592].