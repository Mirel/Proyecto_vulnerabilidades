# Caso 1 — Análisis de CVE: Dirty COW (CVE-2016-5195) — ejemplo de estudio

> Nota: este fichero resume un caso real como ejercicio de análisis académico. No se incluyen exploits completos.

## 1. Contexto
- **CVE:** CVE-2016-5195  
- **Descripción:** Vulnerabilidad de race condition en el subsistema de copy-on-write del kernel Linux (mmap / write).  
- **Impacto:** Escalada de privilegios local a root.

## 2. Objetivo del análisis
- Entender la root cause (race condition en COW).  
- Reproducir el fallo en un entorno controlado (VM con versión vulnerable) y documentar mitigaciones.

## 3. Recursos consultados
- Write-ups y documentación (enlace 1, enlace 2).  
- Parche del kernel (referencia a commit).

## 4. Pasos realizados
1. **Preparación del entorno**
   - VM Debian con kernel vulnerable (snapshot inicial).
2. **Reconocimiento**
   - Verificar versión del kernel: `uname -a`
3. **Reproducción**
   - Usar PoC público (solo en laboratorio) para reproducir elevación.
   - Ejecutar en VM y observar comportamiento.
4. **Análisis técnico**
   - Revisar código fuente del kernel en el área `mm/` relacionado con `mmap` y `copy_on_write`.
   - Usar `git diff` entre versión vulnerable y parcheada para localizar los cambios.
5. **Mitigación**
   - Aplicar parche del kernel o actualizar paquete de distribución.
   - Verificar que tras parche, PoC no funciona.

## 5. Resultados y lecciones
- Root cause: falta de sincronización en write path de COW.  
- Mitigación: parchear kernel y aplicar políticas de mínimo privilegio.  
- Lección: race conditions requieren pruebas de concurrencia y revisión cuidadosa del locking.

## 6. Evidencias (en repo)
- enlaces a logs/outputs en `evidencia/`  
- referencias a commits y parches aplicados
