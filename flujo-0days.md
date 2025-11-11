# 🧬 Flujo Práctico de Investigación de 0-Days

---

## 1️⃣ Fuzzing Inteligente (AFL++)

**Objetivo:** provocar crashes mediante entradas mutadas automáticamente.

### Configuración del entorno:
```bash
sudo apt install afl++
afl-cc vuln.c -o vuln_afl
mkdir inputs outputs
echo "AAAA" > inputs/seed.txt
afl-fuzz -i inputs -o outputs ./vuln_afl
