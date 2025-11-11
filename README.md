# 🧠 Metodología de Análisis de Vulnerabilidades y Explotación

**Autor:** Mirelle Candida 
**Fecha:** 10/2025  

---

## 🎯 Objetivo del proyecto

Desarrollar una propuesta técnica completa que refleje la metodología y mentalidad profesional de un analista de vulnerabilidades, integrando fases de detección, análisis, explotación y documentación.  
El trabajo combina teoría, práctica real, ejemplos de vulnerabilidades y un flujo detallado para 0-days.

---

## ⚙️ Metodología general (4 fases)

1. **Detección:** reconocimiento, escaneo de puertos, fuzzing preliminar y correlación de CVEs.  
2. **Profundización:** análisis estático (reversing con Ghidra) y dinámico (GDB/x64dbg).  
3. **Síntesis:** desarrollo de PoCs, payloads, bypasses y pruebas controladas.  
4. **Documentación:** reporte técnico, evaluación CVSS y mitigación de riesgo.

Más detalle en: [`docs/metodologia.md`](docs/metodologia.md)

---

## 🔬 Casos de estudio

- **Caso 1:** Buffer Overflow en protocolo de red (ej. FreeFloat FTP Server).  
  [Ver análisis completo →](docs/casos/caso-buffer-overflow.md)
- **Caso 2:** Fallo lógico / Use-After-Free (UAF) en binario analizado.  
  [Ver análisis completo →](docs/casos/caso-uaf.md)

---

## 🧩 Aproximación práctica a 0-days

La estrategia combina fuzzing (AFL++), diffing (BinDiff/Diaphora) y reversing avanzado (Ghidra/IDA).  
[Ver flujo completo →](docs/flujo-0days.md)

---

## 📊 Visualización interactiva

He creado una representación visual del flujo de análisis y fases metodológicas:  
➡️ **Abrir versión interactiva:** [`visuals/index.html`](visuals/index.html)

---

## 📁 Estructura del proyecto

