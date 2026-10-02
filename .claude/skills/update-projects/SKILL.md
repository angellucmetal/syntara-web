---
name: update-projects
description: Procedimiento para agregar, actualizar o cambiar de estado un proyecto en la sección "Lo que estamos construyendo" del sitio de Syntara. Usar cuando se mencione un proyecto (SuriMed, 3VT, SuriArq, Epistemium u otro nuevo) que haya que mostrar, describir o pasar de "Próximamente" a "En vivo".
---

# Agregar o actualizar un proyecto

## 1. Juntar la información

No inventar descripciones ni URLs. Buscar en este orden:

1. `docs/projects.md` de este repo.
2. El repo hermano en `C:\Personal\git\<proyecto>`: `README.md`, `CLAUDE.md`, `docs/environment.md` o `docs/pending.md` (ahí suele estar el dominio de producción, normalmente `<proyecto>.syntara.com.ar`).
3. El material en `C:\Users\l_ang\OneDrive\Syntara\<Proyecto>\` (mockups, PDFs, modelos de datos).

Si falta algo (estado real, URL, para quién es), preguntarle a Lucho antes de publicar.

## 2. Elegir el estado

- **En vivo** — tiene dominio funcionando:
  ```html
  <a class="component" href="https://<proyecto>.syntara.com.ar" target="_blank" rel="noopener">
    <div class="chip" aria-hidden="true"></div>
    <div class="body">
      <span class="status">En vivo</span>
      <h3>Nombre</h3>
      <p>Descripción.</p>
    </div>
  </a>
  ```
- **Próximamente** — sin URL pública: mismo markup pero `<div class="component upcoming">`, sin `href`, con `<span class="status">Próximamente</span>`.

Para un estado nuevo (ej. "Beta"), agregarlo a la tabla de estados de `docs/projects.md` y, si necesita estilo propio, crear una clase modificadora como `.upcoming` reusando las variables de `:root`.

## 3. Escribir la descripción

Seguir la skill `site-conventions`: una oración, para quién es y qué resuelve, sin stack técnico, con voseo.

## 4. Actualizar la documentación

- `docs/projects.md`: fila de la tabla + entrada en "Descripciones" con la fuente usada.
- `docs/decisions.md`: solo si hubo una decisión nueva (estado nuevo, cambio de orden, etc.), no por cada alta.

## 5. Verificar

- Que la URL responda (abrirla o `curl -I`).
- Que el orden en `index.html` coincida con `docs/projects.md`.
- Correr el agente `site-reviewer` sobre el diff.
