# Contexto para Archify

## Proyecto y propósito

Práctica 06: Diagrama de Secuencia de Pantallas de una aplicación móvil con 2 roles.
Plataforma de referencia: Mercado Libre. Propuesta académica de marketplace, con identidad y composición simplificadas. El objetivo es visualizar navegación entre pantallas, no llamadas internas a servicios.

Hay 27 pantallas: 7 compartidas, 10 de Comprador y 10 de Vendedor. Cada ID representa una pantalla móvil, no un actor ni un servicio. Usar los mismos IDs y nombres que en [flujo_pantallas.md](../diagramas/flujo_pantallas.md).

## Reglas de experiencia

- Una cuenta puede comprar y vender. S05 (Inicio) es la bifurcación entre roles.
- S01 → S02 → S05 es el acceso principal.
- Registro: S02 → S03 → S05. Recuperación: S02 → S04 → S02; se supone que la persona restablece su contraseña con el enlace enviado.
- S06 y S07 son compartidas y accesibles desde la barra inferior de las pantallas autenticadas.
- Las notificaciones muestran avisos pertinentes a la actividad de la cuenta: compras → C16; ventas → V25.
- La compra avanza desde búsqueda hasta pago confirmado, consulta de compras y seguimiento. C16 → C17 solo ocurre cuando el pedido está entregado. C17 devuelve a C15 al enviar la valoración.
- La publicación avanza desde categoría hasta información, fotografías, precio y confirmación. V23 → V24 es navegación a la lista de ventas; no significa que publicar cause una venta inmediata.
- V24 → V25 requiere una venta existente y con pago confirmado. V26 registra el despacho y permite consultar V27; las estadísticas también se abren desde V18.
- Datos, fotografías, direcciones, precios y cantidades son ficticios. Los controles son representaciones de baja fidelidad; no realizan transacciones.

## Flujos principales

Comprador: S01 → S02 → S05 → C08 → C09 → C10 → C11 → C12 → C13 → C14 → C15 → C16 → C17.

Vendedor: S01 → S02 → S05 → V18 → V19 → V20 → V21 → V22 → V23 → V24 → V25 → V26 → V27.

## Indicación lista para proporcionar a Archify

> Genera un diagrama interactivo de navegación de una aplicación móvil académica inspirada en Mercado Libre. Usa el Mermaid adjunto como fuente de nodos y conexiones y estas reglas como contexto. Conserva las 27 pantallas y sus IDs. Divide el diagrama en Compartidas, Comprador y Vendedor. Representa Inicio como bifurcación; identifica acceso, registro y recuperación. Muestra los recorridos principales con flechas continuas y los regresos y accesos globales con flechas discontinuas. Permite explorar cada pantalla y su rol. Mantén estética de wireframe en blanco, negro y gris. Explica las condiciones “pedido entregado” y “venta existente”. Toma los sketches HTML/CSS como referencia visual. No conviertas esto en un diagrama de servicios o de llamadas a una API.

## Material que se debe adjuntar

1. `diagramas/flujo_pantallas.md`: navegación y catálogo de IDs.
2. `docs/contexto_archify.md`: reglas, alcance y solicitud.
3. `sketches/index.html`, `sketches/styles.css` y `sketches/app.js`, o capturas del tablero: referencia visual.
4. `README.md`: objetivo y presentación de la práctica.

Archify se utilizará en una etapa posterior. Esta entrega prepara su contexto; no incluye un diagrama generado por Archify.
