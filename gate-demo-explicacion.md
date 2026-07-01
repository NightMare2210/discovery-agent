# Demo del Gate — Explicación

## ¿Qué muestra la captura?

La captura documenta el funcionamiento del `readiness-gate`: el hook que impide generar artefactos del MVP cuando la evidencia es insuficiente. Se muestran dos momentos: el bloqueo y la resolución.

---

## Momento 1 — Bloqueo

Se retiró temporalmente la entrevista `gerente-propietaria.md` de la carpeta `interviews/`, simulando el caso en que una persona principal no tiene respaldo de primera mano.

Al intentar escribir `user-stories.md`, el hook intercepta la operación antes de que ocurra y devuelve **exit code 2**, bloqueando la escritura. El mensaje indica exactamente qué falta:

- La persona **G. (gerente / propietaria)** figura como primaria en el `evidence-map.json` pero no tiene entrevista en disco — está "construida de oídas".
- Los **4 dolores** asociados a esa entrevista quedan huérfanos: el sistema los detecta porque citan `gerente-propietaria.md` como fuente, pero ese archivo ya no existe.

El gate no se puede rodear: mientras la evidencia no esté, la escritura no ocurre.

---

## Momento 2 — Resolución

Se restauró `gerente-propietaria.md` a su ubicación original. El hook vuelve a ejecutarse sobre el mismo archivo y esta vez encuentra:

- 3 entrevistas en `interviews/` (supera el mínimo de 2)
- Las 3 personas primarias con entrevista de primera mano en disco
- Los 12 dolores del `evidence-map.json` con fuentes que existen

Resultado: **exit code 0** — la escritura procede sin errores.

---

## ¿Por qué importa esto?

El gate convierte una regla de calidad ("no generes el MVP sin evidencia suficiente") en una restricción ejecutable del proceso. No depende de que el desarrollador recuerde la regla ni de una revisión manual. Si la evidencia no está, el sistema no avanza — y el mensaje de error indica exactamente qué conseguir para desbloquearlo.
