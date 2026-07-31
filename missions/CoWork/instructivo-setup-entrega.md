# 🧭 Misión Faro — instructivo de setup, instalación y entrega

*Paulo Veiga · Marco Sánchez Sorondo · Claudio Righetti · Juan Pablo Cosentino*

Este documento acompaña al enunciado de la misión (`mission-parte1.pdf` y `mission-parte2.pdf`). Acá está el detalle operativo: cómo usar la cuenta del grupo, qué instalar, cómo verificar que todo funciona, y cómo son la presentación de avances y la entrega final.

---

## 1 · La cuenta del grupo

- Cada grupo recibe **una cuenta de Claude ya creada**, con su contraseña. No hace falta registrarse: la cátedra las entrega listas.
- **Todos los integrantes usan la misma cuenta.** Eso significa que el historial de chats, el Project y las Skills son compartidos: lo que hace uno lo ven (y lo pueden pisar) los demás. Coordinen quién trabaja sobre qué antes de empezar.
- La cuenta tiene el **plan básico**, con tokens limitados que se comparten entre todos los integrantes.

### Configuración obligatoria del modelo

Para no agotar los tokens del grupo:

1. En el selector de modelo, elegir **Sonnet**.
2. Poner el nivel de pensamiento en **medio**.
3. Verificar esta configuración cada vez que abran una sesión nueva: nada de la misión necesita un modelo más grande.

> ⚠️ Si el grupo agota los tokens, hay que esperar a que se renueve la ventana de uso. La forma de que no pase es respetar la configuración de arriba y no dejar tareas corriendo sin propósito.

---

## 2 · Instalación

### Parte 1 — el chat (sin instalar nada)

La Parte 1 de la misión se resuelve en **claude.ai** desde el navegador, con la cuenta del grupo. Solo hace falta iniciar sesión. Además, el grupo necesita **una cuenta de Gmail** a mano: la misión trabaja sobre el mail.

### Parte 2 — Claude Cowork

1. Descargar la **aplicación de escritorio de Claude** desde [claude.ai/download](https://claude.ai/download) (Mac o Windows).
2. Instalarla e iniciar sesión con la cuenta del grupo.
3. Abrir **Cowork** desde la aplicación y concederle acceso a una carpeta de prueba cuando la pida.
4. **Probar que Cowork opera la carpeta de verdad:** pedirle que cree un archivo (por ejemplo, "creá un archivo `prueba.md` con la fecha de hoy") y verificar que el archivo aparece en la carpeta.

Este último paso es el importante: instalar suele salir bien, pero al operar una carpeta aparecen los problemas de entorno. Los más comunes:

- **Windows con la virtualización desactivada.** Cowork la necesita para su entorno de trabajo. Se habilita en la configuración del BIOS/UEFI de la máquina (suele figurar como "Intel VT-x", "AMD-V" o "SVM"); si no saben entrar al BIOS, busquen "habilitar virtualización" junto al modelo de su computadora.
- **macOS desactualizado.** Actualizar el sistema operativo desde Ajustes antes de la clase.
- **Permisos de carpeta denegados.** Si el sistema preguntó por acceso a archivos y se respondió que no, volver a conceder el permiso desde la configuración de privacidad.

Todo esto tiene que estar **resuelto antes de llegar a la clase**: no hay tiempo de clase para pelear con el BIOS.

Alcanza con que **una computadora del grupo** tenga Cowork instalado, pero conviene que sean al menos dos: la tarea programada local solo corre con la aplicación abierta.

---

## 3 · Checklist de setup

Verificar cada punto **antes de llegar a la clase**. Si alguno falla, resolverlo antes; los problemas de entorno no se arreglan en clase.

| ✔ | Verificación | Cómo saber que está bien |
|---|---|---|
| ☐ | Sesión iniciada en claude.ai | El chat abre con la cuenta del grupo, no una personal |
| ☐ | Modelo configurado | El selector muestra **Sonnet** con pensamiento **medio** |
| ☐ | Cowork instalado | La app de escritorio abre y Cowork lista la carpeta de prueba |
| ☐ | Cowork opera la carpeta | El archivo de prueba pedido a Cowork aparece en la carpeta |
| ☐ | Cuenta de Gmail | El grupo tiene una y puede iniciar sesión |
| ☐ | Herramienta de grabación | Grabaron y reprodujeron un Loom de prueba de 30 segundos |
| ☐ | Coordinación del grupo | Acordaron quién trabaja sobre qué parte y en qué momento |

---

## 4 · Presentación del día de la misión

El mismo día en que se ponen a resolver la misión, **cada grupo expone**. La presentación tiene que mostrar:

- **La estrategia adoptada:** cómo van a encarar la misión y cómo se repartieron el trabajo.
- **Todos los avances que tengan:** la mayor cantidad posible. Un milestone andando vale más que un plan detallado.

El formato es **libre**: cada grupo presenta con su propio estilo. No hay template.

---

## 5 · Entrega final

La entrega final es **una sola por grupo**: un **Loom** (video con pantalla y voz).

El Loom tiene que contar una **historia de resolución**, no ser una demo suelta. Debe incluir:

1. **El recorrido:** cómo fueron resolviendo el problema, en orden.
2. **Los desafíos:** qué se les trabó y cómo lo destrabaron.
3. **La tarea programada en vivo, de punta a punta:** se ve cómo se dispara, cómo trabaja y cómo el resultado llega a destino. Sin cortes que escondan pasos.
4. **Los aprendizajes:** qué se llevan del trabajo con el agente.

**Cómo entregar:** compartir el enlace del Loom con permiso de visualización abierto (que cualquiera con el enlace pueda verlo) por el canal que indique la cátedra.

---

## 6 · Problemas frecuentes

- **"Cowork no arranca" o "falla al abrir la carpeta" (Windows).** Casi siempre es la virtualización desactivada. Habilitarla en el BIOS/UEFI (ver sección 2) y volver a probar.
- **"Cowork no funciona" (Mac).** Verificar que macOS esté actualizado y que la app tenga permiso de acceso a archivos en la configuración de privacidad.
- **"La tarea programada no corrió."** Las tareas locales de Cowork corren solo con la aplicación abierta. Para la demo del Loom, dispararla a demanda ("Run now") con la app abierta.
- **"No me deja elegir el modelo."** Verificar que la sesión sea la de la cuenta del grupo y no una personal logueada en el mismo navegador.
- **"Nos quedamos sin tokens."** Esperar la renovación de la ventana de uso. Revisar que todos estén en Sonnet con pensamiento medio.
- **"El conector pide autenticación de nuevo."** Rehacer la autenticación desde la biblioteca de conectores; algunas sesiones expiran.
- **"Alguien pisó el trabajo de otro."** El historial es compartido: usar chats separados por tema y avisar en el grupo antes de tocar el Project o las Skills.
