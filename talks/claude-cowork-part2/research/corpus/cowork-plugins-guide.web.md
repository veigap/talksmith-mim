---
source_file: https://claude.com/docs/cowork/guide/plugins
source_type: web-capture
ingested_at: 2026-08-03
---

# Install plugins — Claude Cowork guide (docs oficiales)

## Provenance
- Original location: fetch web directo durante Step 5 (Review), sin captura en research/web/
- Format: html
- Author / source (if known): Anthropic — documentación de Cowork
- Date of original (if known): vigente al 2026-08-03

## Key claims
- Un plugin puede empaquetar cuatro componentes: **Skills** ("Reusable instructions that teach Claude a workflow"), **Connectors** ("MCP servers that give Claude access to an external service"), **Agents** ("Specialized subagents Claude can delegate to") y **Hooks** ("Scripts that run at defined points in a session").
- Instalación: Customize → Plugins → "Browse plugins"; "The default marketplace is Anthropic's official catalog; you can add other marketplaces by URL". También se puede subir un plugin desde archivo.
- Autenticación: "If the plugin includes a connector that needs authentication, you're prompted to sign in."
- Componentes desactivables: "Open the installed plugin to see its skills, connectors, agents, and hooks. Enable or disable individual components as needed."
- Alcance de producto: "Plugins are available in Cowork and Code. They aren't used in Chat."
- Organización: en Team/Enterprise "administrators can require certain plugins for everyone in the organization. Required plugins install automatically [...] you can't remove them."
- Límites: 200 MB por paquete, 5.000 archivos por plugin, 25 marketplaces.

## Definitions and terminology
- **Marketplace:** catálogo de plugins; el default es el oficial de Anthropic.
- **Connector (en un plugin):** servidor MCP que da acceso a un servicio externo.

## Evidence and examples
- Flujo de instalación en cuatro pasos con prompt de sign-in para conectores.

## Inconsistencies / open questions
- Ninguna detectada; confirma y precisa la composición Skills+Connectors+Agents+Hooks que el corpus del chat dejaba abierta.

## Images / diagrams
- Ninguna imagen capturada.

## Raw / preserved excerpts

> "A plugin can bundle: Skills — Reusable instructions that teach Claude a workflow; Connectors — MCP servers that give Claude access to an external service; Agents — Specialized subagents Claude can delegate to; Hooks — Scripts that run at defined points in a session."

> "Open the installed plugin to see its skills, connectors, agents, and hooks. Enable or disable individual components as needed."

> "Administrators can require certain plugins for everyone in the organization. Required plugins install automatically and show 'This plugin is required by your organization'; you can't remove them."
