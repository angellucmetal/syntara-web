---
name: site-conventions
description: Convenciones de diseño, tono y estructura HTML/CSS del sitio de Syntara. Usar siempre que se edite index.html — textos, secciones nuevas, estilos o assets.
---

# Convenciones del sitio — Syntara

## Tono y textos

- Español rioplatense con voseo: "Escribinos", "Contanos", nunca "Escríbenos" ni "Escriba".
- Frases cortas, concretas, sin jerga de marketing vacía. Mismo registro que lo existente: "Automatización aplicada a procesos reales, no a demos de vidriera."
- Descripción de proyecto: una oración (dos como máximo), que diga **para quién es y qué resuelve**, no el stack técnico. Nada de Supabase, Next.js, RLS, etc.
- Nombres propios con su capitalización oficial: SuriMed, SuriArq, 3VT, Epistemium.

## Diseño

- Colores solo vía variables de `:root`. El gradiente de marca es `--grad` (azul → teal → turquesa → verde).
- Títulos en `--font-head` (Poppins 600/700), texto en `--font-sans` (Inter 400/500/600). No agregar otras fuentes ni pesos sin necesidad.
- Bordes redondeados: 12px en tarjetas, 999px en pills/botones.
- Hover de tarjetas: `border-color: var(--turquoise)` + `translateY(-2px)`, transición `.15s ease`. Reusar, no inventar efectos nuevos.
- Animaciones: respetar `prefers-reduced-motion` (ya hay un bloque para `.pulse`).

## Estructura HTML

- Cada sección: `<section>` → `<div class="wrap section-inner">` → `<p class="section-label">` + contenido.
- Componentes existentes para reusar: `.pad` (servicios, grilla de 3), `.component` (proyectos, lista vertical), `.cta` (botón con gradiente), `.status` (pill de estado).
- Links externos: `target="_blank" rel="noopener"`.
- Elementos decorativos con `aria-hidden="true"`; imágenes con `alt`.
- Indentación de 2 espacios, CSS dentro del `<style>` del `<head>`, agrupado por los comentarios `/* ---------- SECCIÓN ---------- */`.

## Antes de dar algo por terminado

- Revisar a 375px de ancho (breakpoint en 760px).
- Si cambió un mail, link o proyecto, verificar que no quedaron instancias viejas (`grep`).
