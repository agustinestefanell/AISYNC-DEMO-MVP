# MVP Handoff Log

## OE-MVP-04 - Simplify Teams Map / Tree

- Fecha: 2026-05-06
- Modelo recomendado/usado: GPTCodex 5.5 recomendado; Codex GPT-5 usado en esta sesion
- Repo confirmado: AISYNC-DEMO-MVP
- Remote confirmado: https://github.com/agustinestefanell/AISYNC-DEMO-MVP.git
- Branch: main
- Commit hash: este mismo commit; hash final reportado al cierre de OE
- Archivos tocados:
  - src/pages/PageD.tsx
  - docs/HANDOFF_MVP.md
- Cambios realizados:
  - Header de Teams simplificado a `Teams`.
  - Copy principal actualizado a `Organize internal AI teams inside this AISync cell.`
  - `Active team` visible siempre, con fallback `none selected`.
  - Copy MAP/TREE agregado para clarificar el modo activo.
  - Cards/nodos reducidos a nombre, tipo SAT/MAT, status, badge Active y botones Open/Edit.
  - Metricas, descripciones largas, tags enterprise y ruido secundario removidos de las cards MVP.
  - `Connect Team` preservado como placeholder Coming Soon sin configuracion real.
  - `Promote Agent` preservado como funcion futura/deshabilitada.
  - Separacion Open/Edit preservada sin cambiar routing, workspace, `activeWorkspaceRootId` ni `selectedNodeId`.
- Validaciones ejecutadas:
  - Verificacion obligatoria de entorno: repo, remote, branch, working tree limpio antes de editar.
  - `node "C:\Program Files\nodejs\node_modules\npm\bin\npm-cli.js" run build`: OK.
  - Revision visual en navegador/headless sobre `http://127.0.0.1:5175/?page=D`: OK para header, Active team, MAP copy y claridad general.
  - Revision de handlers en `PageD.tsx`: Open llama `openTeamWorkspace(node)` y Edit llama `openEditNode(node.id)` en MAP y TREE.
  - `Connect Team` revisado como modal Coming Soon sin flujo de configuracion real.
- Riesgos residuales:
  - Validacion de clicks hecha por revision de handlers y captura headless; no se incorporo una suite E2E automatizada.
  - El TopBar/BottomNav siguen usando la etiqueta historica `Teams Map`, fuera del alcance de OE-MVP-04.
- Proximo paso recomendado:
  - OE-MVP-05 Workspace por team, solo despues de confirmar este cierre en `AISYNC-DEMO-MVP`.

## OE-MVP-04B - Restore Preview Label And Minimal Connect Team

- Fecha: 2026-05-06
- Modelo recomendado/usado: GPTCodex 5.5 recomendado; Codex GPT-5 usado en esta sesion
- Repo confirmado: AISYNC-DEMO-MVP
- Remote confirmado: https://github.com/agustinestefanell/AISYNC-DEMO-MVP.git
- Branch: main
- Commit hash: este mismo commit; hash final reportado al cierre de OE
- Archivos tocados:
  - src/pages/PageD.tsx
  - docs/HANDOFF_MVP.md
- Cambios realizados:
  - Etiqueta `Preview` restaurada en cards/nodos de Teams Map / Tree sin reintroducir metricas falsas.
  - `Connect Team` convertido de Coming Soon a MVP funcional minimo local.
  - Modal simple agregado con `External user email`, `Host local team` y `Connection type`.
  - `Create connection` crea un registro local demo con estado inicial `Pending`.
  - Placeholder externo/conectado visible en Map y Tree tras crear la conexion.
  - No se agregaron permisos reales, backend, repositorio compartido real ni conexiones reales entre usuarios.
  - Open/Edit preservados sin tocar routing, workspace, `activeWorkspaceRootId` ni `selectedNodeId`.
- Validaciones ejecutadas:
  - Verificacion obligatoria de entorno: repo, remote, branch, working tree limpio antes de editar.
  - `node "C:\Program Files\nodejs\node_modules\npm\bin\npm-cli.js" run build`: OK.
  - Revision visual headless sobre `http://127.0.0.1:5175/?page=D`: OK para `Preview`, card limpia y acceso `Connect Team`.
  - Revision de handlers en `PageD.tsx`: `Create connection` actualiza `externalConnection`; Map y Tree reciben ese placeholder.
  - Revision de handlers Open/Edit: MAP y TREE mantienen Open hacia `openTeamWorkspace(node)` y Edit hacia `openEditNode(node.id)`.
- Riesgos residuales:
  - La conexion es solo mock/demo en memoria local de la pantalla; no persiste en storage ni backend.
  - La validacion de click completo fue por revision de handlers y captura headless; no se agrego suite E2E automatizada.
- Proximo paso recomendado:
  - Definir persistencia local del connection record o criterio de demo por sesion antes de avanzar a permisos reales.
