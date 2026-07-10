# Conclusions

## El loop completo y la idea para llevarse

- Lo que construimos, punta a punta — el loop de Atlas combinando todas las piezas:

```ascii
Lunes 8:00
   |
   v
[Schedule] dispara
   |
   v
[Skill buscar-accion] --(Connector MT Newswires + web_fetch Yahoo)--> guarda fuentes/
   |
   v
[Skill reporte-semanal] consolida --> reporte .md en el Project
   |
   +--> [Connector Gmail] deja borrador para el equipo
   |
   v
[Skill publicar-tablero] --> Live Artifact pulso-semanal-FECHA (pestaña Live artifacts)
```

- **Las piezas, una línea cada una:** Instrucciones (el contrato) · Projects (el lugar fijo) · Skills (enseñar una vez) · Connectors/MCP (las manos) · Schedule (que corra solo) · Live Artifacts (compartir el resultado).
- **La idea para llevarse:** *"Todo lo que le explicás a Claude dos veces es una Skill que deberías escribir una vez."* Y el gancho: *"Acaban de automatizar un reporte que les iba a comer la mañana de cada lunes. ¿Qué otra tarea recurrente podrían delegarle a su propio Atlas?"*

### Notes

Cierre integrador: mostrar el diagrama del loop completo para que vean cómo cada pieza que aprendimos se engancha con la siguiente. Repasar las seis piezas en una línea cada una. Cerrar con las dos frases ancla: la de la Skill ("enseñá una vez") y el gancho que los invita a pensar qué tarea propia delegarían. Tiempo objetivo: ~5 min + Q&A.
