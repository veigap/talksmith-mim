# 🧹 Misión 0: el escritorio del pasante

*Entorno introductorio a Claude Cowork, dentro del universo de la misión Faro. Se hace guiado en clase, al arrancar la Parte 2; dura 20 a 30 minutos.*

---

## 🎬 La situación

El pasante de **Atlas** terminó su pasantía el viernes. Antes de irse te dejó su carpeta de trabajo de la última semana, con una nota de disculpas: números que no le cierran, un borrador del pulso a medio terminar, archivos con nombres tipo "FINAL final" y un formato viejo dando vueltas. La reunión de los lunes no espera.

Es tu primer trabajo con Cowork: ordenar ese escritorio **con el agente**, aprobando cada acción, y salir con el pulso de la semana listo en el formato que exige el jefe.

## 📁 La carpeta

`escritorio-del-pasante/`, cinco archivos, cuatro formatos:

| Archivo | Qué es |
|---|---|
| `cotizaciones semana (1).xlsx` | Los cierres de YPF, Vista y Tenaris de la semana, con las variaciones calculadas a mano por el pasante |
| `Pulso semanal - FINAL final.docx` | El borrador del pulso, a medio terminar y con el formato viejo |
| `guia-formato-pulso_v3.pdf` | La guía vigente del jefe: 5 secciones obligatorias, envío lunes 8:00 |
| `notas-del-pasante.md` | Sus notas de salida, con las pistas de lo que quedó mal |
| `Copia de notas viejas (recuperado).txt` | El formato anterior, desactualizado, que contradice a la guía |

Los archivos se referencian entre sí: ninguna pregunta interesante se responde leyendo uno solo. Hay **4 errores plantados**, todos detectables cruzando documentos; las notas del pasante los insinúan porque esto no es un examen: es práctica del ciclo **pedir → supervisar → verificar**.

> ♻️ **Regenerable.** `python3 gen_escritorio_pasante.py` reconstruye la carpeta desde cero. Rompela sin miedo: se rehace en segundos. Trabajá siempre sobre una copia dentro de tu carpeta concedida.

## 🪜 Los cinco ejercicios

Cada uno ejercita una capacidad del agente que después usás en la misión Faro. Cowork en modo **Ask**: el agente propone, vos aprobás.

**1 · Analizar la carpeta.** Concedé la carpeta y pedí: *"¿Qué hay acá, en qué estado está cada archivo y qué quedó pendiente?"*. El agente lee los cinco archivos, en cuatro formatos, y te devuelve el mapa.
*Capacidad: lectura y comprensión de un entorno de archivos completo.*

**2 · Ordenar y renombrar.** Pedile un criterio de nombres y aplicalo. Cada renombre pasa por tu aprobación; rechazá al menos uno para ver qué pasa.
*Capacidad: acciones sobre el sistema de archivos con aprobación humana.*

**3 · Completar el borrador.** La sección "Qué vigilar" del pulso está vacía. Pedile que la complete usando la información de los demás archivos, respetando el tono del documento.
*Capacidad: edición de un documento existente respetando su contexto.*

**4 · Consolidar en `.md` y exportar al final.** Pedile el pulso completo de la semana como `pulso-semanal.md`, con las 5 secciones de la guía v3, cruzando planilla + borrador + noticias. Cuando esté aprobado, y solo entonces: *"generame el PDF"*.
*Capacidad: crear conocimiento nuevo desde fuentes múltiples; el flujo trabajar-en-md, exportar-al-final.*

**5 · Auditar y corregir.** Pedile: *"revisá la consistencia de toda la carpeta: números, afirmaciones y versiones. Listá lo que no cierra antes de tocar nada"*. Debe encontrar los 4 errores; vos decidís qué se corrige.
*Capacidad: verificación cruzada; la salida de la IA no se acepta, se verifica.*

**🏁 Lo lográs cuando:** la carpeta quedó ordenada con criterio, el `pulso-semanal.md` respeta la guía v3 con los números corregidos, y podés decir cuáles eran los 4 errores y cómo los detectó (o no) el agente.

## 🔎 Los 4 errores, para el facilitador

<details>
<summary>Spoiler (abrir después del ejercicio 5)</summary>

1. **Variación mal calculada** (`cotizaciones semana (1).xlsx`): YPF figura +1,2%; con cierres 42,10 vs 40,85 la variación real es **+3,1%**.
2. **Total que no suma** (misma planilla, hoja Volumen): el total dice 19,7; la suma real es **20,7**.
3. **Afirmación que contradice los datos** (`Pulso semanal - FINAL final.docx`): el resumen dice que "las tres empresas cerraron al alza"; Tenaris cerró **-0,8%**.
4. **Versión desactualizada** (`Copia de notas viejas (recuperado).txt`): describe el formato viejo (viernes, 3 secciones, sin aclaración legal); la guía v3 vigente exige lunes 8:00, 5 secciones y aclaración legal obligatoria.

</details>

## ➡️ Y después

El `pulso-semanal.md` con el que terminás es exactamente el punto de partida del **Milestone 3** de la misión Faro: ya conocés el formato objetivo, ya aprobaste acciones del agente y ya auditaste su salida. Lo que sigue es volverlo repetible: Project, Instrucciones y el resto de la misión.

---

*Filosofía de diseño adaptada del entorno `caso_finanzas_desordenado` (DIAA2026): carpeta chica pero completa, formatos mixtos, referencias cruzadas, errores plantados verificables, aprobación humana y regeneración por script.*
