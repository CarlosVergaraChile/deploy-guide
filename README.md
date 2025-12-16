# Deploy Guide - Proyectos CarlosVergaraChile

Guía completa de despliegue usando opciones gratuitas y cuentas existentes.

## 📋 Tabla de Opciones de Deploy

| Proyecto | Tipo | Opción Recomendada | Costo | Estado |
|----------|------|------|------|--------|
| **SAM v3.0** | Frontend (Node/SPA) | Vercel | Gratis | 🚀 Deploy en progreso |
| **cosas-i-doodle-shop** | Frontend estático (HTML/CSS/JS) | GitHub Pages | Gratis | 🚀 Deploy en progreso |
| **marketing-digital-standard** | Documentación (Markdown) | GitHub Pages | Gratis | ✅ Listo |
| **payment-gateway-standard** | Librería/NPM | npm registry | Gratis | 📦 Listo para publicar |
| **gl-strategic-website** | Frontend (HTML/CSS/JS) | GitHub Pages o Hostinger | Gratis/Ya pagado | Revisar |
| **gl-strategic-mvp** | Backend (Python/Framework) | Google Cloud Run (uchile.cl) | Gratis (300 USD/mes) | 🔧 Configurar |

---

## 🚀 1. SAM v3.0 - Deploy en Vercel (Recomendado para Node)

### Opción A: Deploy desde GitHub (Automático)

```bash
# 1. Ya está en GitHub: https://github.com/CarlosVergaraChile/SAM-v3.0-AI-Teacher
# 2. Ir a https://vercel.com/new
# 3. Importar repo de GitHub
# 4. Vercel detectará automáticamente index.html
# 5. Configurar variables de entorno:
#    - GEMINI_API_KEY
#    - MERCADO_PAGO_PUBLIC_KEY (o Flow, Global66 keys)
# 6. Hacer click en "Deploy"
```

**Resultado**: Tu app estará en `sam-v3-0-ai-teacher.vercel.app`

**Alternativa**: Si quieres usar Hostinger (que ya tienes):

```bash
# 1. Descargar repo en ZIP
# 2. Subir via FTP a: /sam-v3-0/
# 3. Acceso en: tudominio.com/sam-v3-0/
```

---

## 🚀 2. cosas-i-doodle-shop - GitHub Pages (Gratis, Estático)

### Paso a Paso:

```bash
# 1. Ya está en GitHub
# 2. Ir a Settings → Pages
# 3. Source: Deploy from branch
# 4. Branch: main → /root (o /docs si lo prefieres)
# 5. Save
```

**Resultado**: Tu tienda en `carlosvergarachile.github.io/cosas-i-doodle-shop`

**Configuración recomendada en index.html:**

```html
<script>
  // Cambiar BASE_URL en config.js según deploy:
  // GitHub Pages: /cosas-i-doodle-shop/
  // Hostinger: /cosas-i-doodle/
  const BASE_URL = '/cosas-i-doodle-shop/';
</script>
```

---

## 🚀 3. marketing-digital-standard & payment-gateway-standard

Ya están publicados en GitHub (README visible públicamente).

### Para NPM Registry (payment-gateway-standard):

```bash
# Si quieres publicar como librería npm:
cd payment-gateway-standard
npm login  # usa tu cuenta
npm publish

# Luego otros proyectos pueden:
npm install payment-gateway-standard
```

---

## 🔧 4. gl-strategic-mvp - Google Cloud Run (Con Universidad de Chile)

### Requisitos:
- Cuenta Google Cloud con `uchile.cl` (tienes acceso)
- API keys de proyectos (free tier: $300/mes)

### Deploy en 5 pasos:

```bash
# 1. Ir a: https://console.cloud.google.com
# 2. Seleccionar proyecto o crear: "gl-strategic-mvp"
# 3. Navegar a Cloud Run → Crear servicio
# 4. Source: Deploy uno existente (GitHub)
# 5. Conectar repo + seleccionar Dockerfile
```

**Costo**: Gratis (free tier: 180,000 vCPU-seconds/mes = ~45,000 req/mes)

---

## 🌐 5. Hostinger (Ya tienes cuenta)

Para cualquier proyecto que no sea de frontend puro:

### Acceso vía FTP:

```bash
# Credenciales (ya las tienes en Hostinger):
Host: tudominio.com
User: tu_usuario_ftp
Password: tu_password
Port: 21

# Estructura recomendada:
/public_html/
  ├── index.html (página principal)
  ├── sam-v3-0/ (SAM v3.0)
  ├── doodle/ (cosas-i-doodle-shop)
  └── admin/ (paneles administrativos)
```

---

## 📊 Matriz de Decisión Rápida

### Tipo de Proyecto → Plataforma

| Característica | GitHub Pages | Vercel | Google Cloud | Hostinger |
|---|---|---|---|---|
| HTML/CSS/JS puro | ✅ Mejor | ⚠️ Overkill | ❌ No | ✅ OK |
| Node.js/Next.js | ❌ No | ✅ Mejor | ⚠️ Complejo | ❌ No |
| Python/Django | ❌ No | ❌ No | ✅ Mejor | ⚠️ Soporte |
| Costo | 🟢 $0 | 🟢 $0 | 🟢 $0 (free tier) | 🟠 Ya pagado |
| Facilidad | 🟢 Muy fácil | 🟢 Fácil | 🔴 Difícil | 🟡 Medio |
| Escalabilidad | 🟡 Limitada | 🟢 Buena | 🟢 Excelente | 🟡 Limitada |

---

## ✅ Checklist de Deploy Recomendado

### SAM v3.0
- [ ] Crear cuenta/acceso Vercel (gratis)
- [ ] Conectar GitHub repo
- [ ] Configurar env variables (GEMINI_API_KEY, etc)
- [ ] Deploy automático al hacer push a main
- [ ] Probar en https://sam-v3-0-ai-teacher.vercel.app

### cosas-i-doodle-shop
- [ ] Ir a GitHub repo Settings → Pages
- [ ] Habilitar GitHub Pages desde main branch
- [ ] Actualizar URLs en config.js para paths relativos
- [ ] Probar en https://carlosvergarachile.github.io/cosas-i-doodle-shop

### payment-gateway-standard (librería)
- [ ] Actualizar versión en package.json
- [ ] Publicar en npm (opcional)
- [ ] Documentar instrucciones de instalación

### marketing-digital-standard
- [ ] Ya está publicado en GitHub (README visible)
- [ ] Considerar crear sitio estático con documentación

### gl-strategic-mvp
- [ ] Configurar Google Cloud con credenciales uchile.cl
- [ ] Crear Dockerfile si no existe
- [ ] Deploy en Cloud Run
- [ ] Configurar domain: `gl-strategic.appspot.com`

---

## 🔐 Variables de Entorno por Proyecto

### SAM v3.0 (.env)

```env
GEMINI_API_KEY=tu_key_de_gemini
PAYMENT_PROVIDER=flow  # o mercadopago, paypal, global66
FLOW_MERCHANT_ID=tu_id
FLOW_API_KEY=tu_key
BASE_URL=https://sam-v3-0-ai-teacher.vercel.app/
```

### cosas-i-doodle-shop (.env en config.js)

```javascript
const CONFIG = {
  MERCADO_PAGO_PUBLIC_KEY: 'tu_public_key',
  BASE_URL: '/cosas-i-doodle-shop/',
  EMAILJS_SERVICE: 'service_xxx',
  EMAILJS_TEMPLATE: 'template_yyy'
}
```

---

## 🎯 URLs de Deploy Esperadas

Una vez completado:

| Proyecto | URL |
|----------|-----|
| SAM v3.0 | `https://sam-v3-0-ai-teacher.vercel.app` |
| cosas-i-doodle-shop | `https://carlosvergarachile.github.io/cosas-i-doodle-shop` |
| gl-strategic-mvp | `https://gl-strategic-mvp.appspot.com` (si Cloud Run) |
| marketing-digital-standard | GitHub (visible en repo) |
| payment-gateway-standard | NPM registry (si publicado) |

---

## 🆘 Troubleshooting

### GitHub Pages no aparece
- Ir a Settings → Pages
- Asegurar que Branch está seteado a `main`
- Esperar 1-2 minutos

### Vercel deploy falla
- Revisar logs en Dashboard de Vercel
- Confirmar que package.json está en root
- Verificar variables de entorno seteadas

### Rutas relativas roten en GitHub Pages
- Cambiar de `/path` a `./path`
- Asegurar que index.html está en raíz del branch

### Google Cloud Run lento
- Aumentar memoria/CPU en configuración
- Usar caché en Dockerfile
- Considerar usar Regional (más cercano a Chile)

---

## 📞 Contacto & Soporte

- Gmail: carlosvergarachile@uchile.cl
- GitHub: @CarlosVergaraChile
- Documentación adicional en cada repo
