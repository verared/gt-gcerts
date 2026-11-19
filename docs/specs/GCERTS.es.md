# Especificación GCERTS — Validez temporal de certificados (EXPERIMENTAL)

- **Estado: EXPERIMENTAL** — separado del núcleo normativo ·
  **Versión:** 1.0.0 · **Línea base:** GUS v3.1.1
- **Edición consolidada:** [`../spec/gus-3.0.0.md`](../spec/gus-3.0.0.md) (§13.4)
- **Licencia:** CC-BY-4.0 · Mantenida por: verared contributors

> **Este perfil NO forma parte de la garantía de conformidad del
> calendario ni de la marca canónica.** No existe implementación de
> referencia en este repositorio; la especificación declara el contrato
> para implementaciones futuras.

## 1. Alcance

Perfiles de **validez temporal de certificados** sobre coordenadas GUS:
ventanas de vigencia expresadas en la escala TCJ/TAI (no en UTC
civil), evaluables offline y con el mismo determinismo que el resto
del estándar.

## 2. Reglas previstas

1. La vigencia se expresa como el intervalo cerrado de instantes GUS
   `[not_before, not_after]` (segundos int64 + nanos), nunca como fechas
   civiles ambiguas.
2. La comprobación de vigencia es una comparación entera pura,
   reproducible en cualquier plataforma y sin acceso a red.
3. La renovación y la revocación son eventos con sello (dominio GST)
   anclables al notario diario; la historia de estados de un
   certificado es una cadena verificable.
4. La caducidad NO se prorroga por zonas horarias ni por cambios
   civiles: la ventana es invariante aunque cambie la legislación de
   horario de la jurisdicción del emisor.
5. Un certificado caducado no se «revalida»: se emite uno nuevo; la
   verificación de firmas históricas usa el material de la época.

## 3. Fuentes de verdad

Todavía ninguna: la spec es la fuente (Sección 13.4 de la edición
consolidada).

## 4. Vectores aplicables

Ninguno todavía en este repositorio.

## 5. Madurez y límites

- **Experimental.** No forma parte de la garantía de conformancia.
- GUS/GCERTS no sustituyen a una PKI operativa ni a los controles de
  seguridad del sistema operativo; describen la dimensión temporal que
  una PKI puede consumir de forma verificable.

## 6. Referencias

- Sección 13.4 de la edición consolidada; `docs/spec/threat-model.md`.
