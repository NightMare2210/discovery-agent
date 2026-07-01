# Reflexión — Discovery Agent sobre inmobiliaria-azuay

**Unidad 1 · Ingeniería de Software · Maestría en Software, UPS**

---

## 1. ¿Qué supuesto tuyo sobre el problema cambió al revisar la evidencia real?

Cuando empecé a pensar en el caso di por sentado que el actor central era el asesor. Es quien más interactúa con el sistema, el que lo usa todo el día. Entonces asumí que el problema principal era operativo: que necesitaba mejores herramientas para gestionar su cartera.

Pero al revisar la evidencia, el dolor más concreto apareció del lado del cliente comprador. Una persona que manejó cuarenta minutos para visitar una propiedad que ya estaba reservada, sin que nadie le hubiera avisado. Eso no es un problema de usabilidad ni de features — es un problema de confianza. Y si el cliente no confía en la información que muestra la plataforma, todo lo demás que construyas encima no sirve.

Lo que cambió fue darme cuenta de que el problema más urgente no siempre está donde uno mira primero. La evidencia te obliga a salir de las suposiciones y escuchar lo que realmente duele.

---

## 2. ¿Qué fue lo más difícil de cumplir la regla de "cero invención"?

Lo más difícil fue frenar el impulso de completar lo que la evidencia no decía.

El dueño del inmueble apareció mencionado en dos entrevistas: en la del asesor y en la de la gerente. Dos menciones concretas. Y en algún momento pensé: "es obvio lo que quiere el dueño, no necesito entrevistarlo para saberlo."

Ahí está exactamente el problema. Eso no es evidencia — es una suposición disfrazada de evidencia. El sistema lo registró como persona `referenciada`, sin respaldo de primera mano, y por eso no pudo sustentar ninguna funcionalidad del MVP.

La lógica del "es obvio" se siente muy convincente. Pero lo que asumís de alguien puede ser completamente distinto a lo que esa persona realmente experimenta. Sin la entrevista, no sabés. La regla no se cumple solo porque uno quiera cumplirla — se cumple cuando el proceso te lo exige y no te deja avanzar hasta que la evidencia esté.

---

## 3. ¿Para qué te serviría la idea de "gobernanza ejecutable" en tu trabajo?

Uno de los problemas más comunes en proyectos reales es que los acuerdos de calidad duran hasta la primera presión de tiempo. "Vamos a escribir tests", "no vamos a mezclar capas" — esos compromisos se sostienen bien al inicio y se diluyen cuando hay urgencia.

La gobernanza ejecutable convierte esos acuerdos en restricciones reales del proceso, no en recomendaciones que dependen de que alguien se acuerde. En este proyecto lo vi funcionar con los gates: si la evidencia no alcanza, el sistema bloquea y no hay forma de rodearlo. Tenés que resolver el problema real.

Eso es aplicable en cualquier equipo. Un hook que bloquee un commit sin tests, una validación que rechace una entrega con campos vacíos — no como castigo, sino como el proceso haciendo cumplir lo que el equipo acordó que importa. Elimina la negociación con uno mismo en el momento de menos energía, que es exactamente cuando más se necesita.
