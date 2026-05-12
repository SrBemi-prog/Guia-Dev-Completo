# 15 — Ciberseguridad para Devs

> No vas a ser hacker, pero TODO dev tiene que saber seguridad básica.

⚠️ **Importante:** Hacking ético = con permiso. Sin permiso es delito.

---

## 🎯 Lo que TODO dev debe saber

### OWASP Top 10 (las vulnerabilidades más comunes)

1. **Injection** (SQL injection)
2. **Broken Authentication**
3. **Sensitive Data Exposure**
4. **XML External Entities (XXE)**
5. **Broken Access Control**
6. **Security Misconfiguration**
7. **Cross-Site Scripting (XSS)**
8. **Insecure Deserialization**
9. **Components with Known Vulnerabilities**
10. **Insufficient Logging**

🔗 https://owasp.org/Top10/

---

## 🛡️ Reglas de oro de seguridad web

1. **Nunca confíes en input del usuario.** Validá TODO en el backend.
2. **No guardes contraseñas en texto plano.** Usá bcrypt/argon2.
3. **Usá HTTPS siempre.** Cloudflare/Let's Encrypt es gratis.
4. **No commitees `.env` ni secrets.** Usá `.gitignore`.
5. **Mantené dependencias al día.** `npm audit`, `dependabot`.
6. **Principio de menor privilegio.** Solo permisos necesarios.
7. **Rate limiting** en endpoints sensibles.
8. **Logueá** pero NUNCA passwords/tokens.

---

## 🔓 Tipos de ataques que tenés que conocer

### SQL Injection
```sql
-- ❌ Inseguro
"SELECT * FROM users WHERE name = '" + input + "'"

-- ✅ Seguro (parametrizado)
"SELECT * FROM users WHERE name = ?"
```

### XSS (Cross-Site Scripting)
- Filtrar HTML del usuario
- React/Vue escapan por defecto
- Cuidado con `dangerouslySetInnerHTML`

### CSRF (Cross-Site Request Forgery)
- Usar tokens CSRF
- SameSite cookies

### Man-in-the-Middle
- Solucionado con HTTPS

---

## 📚 Cursos y recursos

### Para devs
- 📺 [Web Security - HackTricks](https://book.hacktricks.xyz/)
- 📖 [PortSwigger Web Security Academy](https://portswigger.net/web-security) ⭐ GRATIS
- 📺 [Curso Hacking Ético - S4vitar](https://www.youtube.com/@s4vitar)
- 📖 [OWASP Cheat Sheets](https://cheatsheetseries.owasp.org/)

### Hacking ético
- 📺 [HackTheBox](https://www.hackthebox.com/) — máquinas para hackear (legal)
- 📺 [TryHackMe](https://tryhackme.com/) — más amigable que HTB
- 🎓 **OSCP** (certificación pro, cara pero respetada)
- 🎓 **eJPT** (entry level)

---

## 🔍 Tools del trade

### Para devs (defensivo)
- **Snyk** — escanea vulnerabilidades en deps
- **SonarQube** — análisis de código
- **GitGuardian** — detecta secrets commiteados
- **Dependabot** — updates automáticos

### Para pentesters (ofensivo, con permiso)
- **Burp Suite** — proxy web
- **Nmap** — escanear redes
- **Metasploit** — framework de exploits
- **Wireshark** — análisis de tráfico
- **John the Ripper / Hashcat** — cracking de hashes

---

## 🛂 Autenticación: lo que TENÉS que saber

### Passwords
```javascript
// ✅ Bien
import bcrypt from 'bcryptjs';
const hashed = await bcrypt.hash(password, 12);
const valid = await bcrypt.compare(input, hashed);
```

### JWT (JSON Web Tokens)
- Para stateless auth
- Cortos en vida (15-60 min)
- Refresh tokens para sesiones largas

### OAuth 2.0
- Login con Google/GitHub/etc.
- Usá librerías probadas, no la hagas a mano

### MFA / 2FA
- TOTP (Google Authenticator)
- WebAuthn / Passkeys (lo moderno)

---

## 🎓 Certificaciones (para carrera en seguridad)

| Cert | Nivel | Precio aprox |
|------|-------|--------------|
| eJPT | Junior | USD 250 |
| Security+ (CompTIA) | Junior/Medio | USD 400 |
| OSCP | Medio/Senior | USD 1600 |
| CEH | Medio | USD 1200 |
| CISSP | Senior | USD 750 |

---

## 🎯 Proyectos para practicar

1. Hacé una app con login seguro (bcrypt + JWT)
2. Implementá rate limiting en una API
3. Resolvé 5 retos en PortSwigger Web Security Academy
4. Capturá una flag en TryHackMe (sala "Web Fundamentals")
5. Configurá CSP headers en una web
6. Auditá tu propio repo con `npm audit` y arreglá todo
