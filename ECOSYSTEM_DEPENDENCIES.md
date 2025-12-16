# Mapa de Dependencias - Ecosistema Integrado

## 12 Repositorios - Relaciones y Flujos

### Tabla de Dependencias

| Repositorio | Tipo | Dependencias | Usuarios |
|-------------|------|--------------|----------|
| **SAM-v3.0-AI-Teacher** | Plataforma central | course-module, payment-gateway, seasonal-market, maquina-orquestadora | Docentes, estudiantes |
| **Proyecto-Sence-2026** | Curso especializado | course-module, payment-gateway, SAM (opcional) | Trabajadores minería/industria |
| **course-module-standard** | Estándar/Plantilla | Nada | SAM, Proyecto-Sence |
| **payment-gateway-standard** | Librería de pagos | Nada | SAM, Sence, doodle-shop, GL Strategic |
| **seasonal-market-standard** | Análisis temporal | Nada | SAM, marketing-digital |
| **marketing-digital-standard** | Estrategia marketing | seasonal-market | Todos los proyectos |
| **maquina-orquestadora-gl-strategic** | Orquestación IA | Nada (central) | SAM, GL Strategic MVP |
| **gl-strategic-mvp** | Plataforma consultoría | payment-gateway, marketing-digital, maquina-orquestadora | Empresas en transformación |
| **cosas-i-doodle-shop** | E-commerce | payment-gateway, marketing-digital, seasonal-market | Compradores de ilustraciones |
| **lean-healthcare-manual** | Recurso educativo | Nada | Estudiantes, profesionales salud |
| **deploy-guide** | Documentación deploy | Nada (referencia) | Todos los repositorios |
| **Doodle** | Privado/Assets | Nada | cosas-i-doodle-shop |

## Flujos de Integración por Capa

### Capa 1: Contenidos Reutilizables (Estándares)
```
course-module-standard
  ↓ (usado por)
  ├─→ SAM v3.0 (genera contenido)
  └─→ Proyecto-Sence-2026 (estructura 4 módulos)
```

### Capa 2: Monetización
```
payment-gateway-standard
  ↓ (integrado en)
  ├─→ SAM v3.0 (sistema de créditos)
  ├─→ Proyecto-Sence-2026 (si hay cobro)
  ├─→ cosas-i-doodle-shop (carrito de compra)
  └─→ GL Strategic MVP (proyectos pagos)
```

### Capa 3: Análisis de Mercado
```
seasonal-market-standard
  ↓ (informador de)
  ├─→ SAM v3.0 (demanda temporal de cursos)
  ├─→ marketing-digital-standard (estrategia por temporada)
  └─→ cosas-i-doodle-shop (demanda de ilustraciones)
```

### Capa 4: Marketing Integrado
```
marketing-digital-standard
  ↓ (distribuye y posiciona)
  ├─→ SAM v3.0
  ├─→ Proyecto-Sence-2026
  ├─→ cosas-i-doodle-shop
  └─→ GL Strategic MVP
```

### Capa 5: Orquestación Central
```
maquina-orquestadora-gl-strategic
  ↓ (coordina)
  ├─→ SAM v3.0 (control de modelos IA)
  └─→ GL Strategic MVP (backend inteligente)
```

## Matriz de Integración Rápida

Si necesitas integrar X con Y, usa:

**SAM ← → course-module**: Importa plantillas de CMS  
**SAM ← → payment-gateway**: Configura Flow/Mercado Pago  
**Sence ← → SAM**: Crea módulos especializados  
**doodle ← → payment**: Procesa compras  
**GL ← → orchestrator**: Coordina respuestas IA  
**Todos ← → marketing**: Posiciona en buscadores  

## Verificación: 12 Repos Integrados

✅ SAM-v3.0-AI-Teacher  
✅ Proyecto-Sence-2026  
✅ course-module-standard  
✅ payment-gateway-standard  
✅ seasonal-market-standard  
✅ marketing-digital-standard  
✅ maquina-orquestadora-gl-strategic  
✅ gl-strategic-mvp  
✅ cosas-i-doodle-shop  
✅ lean-healthcare-manual  
✅ deploy-guide  
✅ Doodle (privado)  

**Estado**: Ecosistema de 12 repos completamente mapeado y documentado
