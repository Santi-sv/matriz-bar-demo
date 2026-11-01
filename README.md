# Matriz Bar — demo interactiva

[Ver la demo](https://Santi-sv.github.io/matriz-bar-demo/)

Sitio estático para probar en celular y computadora. **Todos los datos operativos son ficticios, no se envían mensajes ni se realizan cobros.** Cada sesión es independiente y los cambios se reinician al recargar.

## Publicación

GitHub Pages sirve la raíz de `main`, sin instalación ni build. El archivo `.nojekyll` permite servir los archivos estáticos directamente. Las fotos y los iconos son locales; las fuentes usan Google Fonts con fuentes de respaldo.

Para probar localmente, abrir `index.html` o ejecutar `python3 -m http.server 8000` y visitar `http://localhost:8000/`.

## Guía de la demo

## Qué tiene
- **Site do cliente** (`#site`): hero con foto, cardápio real (petiscos, coquetéis, chopes, vinhos, sem álcool) con carrito (entrega/retirada, bairro, pagamento), reservas (data, pessoas, área, horários).
- **Painel do restaurante** (`#painel`): KPIs, kanban de pedidos, tabla de reservas con ocupación por horario, canales (WhatsApp Business, Instagram, e-mail) con automatizaciones y log de mensajes.
- Previews de lo que recibe el cliente: chat de WhatsApp y e-mail.

## Marca
- Óxido `#964A2D`, azul marino `#123044` (sacados del logo). Fondo neutro `#F2F4F6`.
- Títulos: Ultra (slab tipo Clarendon, como el logo). Subtítulos: Roboto Slab. Texto: Figtree.
- Logo, lettering "PETISCOS"/"BAR" y fotos de Instagram en `assets/`.
- Soporta modo claro/oscuro vía tokens CSS en `:root`.

## Datos reales vs ejemplo
- Real: nombre, @matrizbar, carta y precios (stories de Instagram), fotos, participación en São Sebastião Restaurant Week (hasta 15/11).
- Ejemplo (confirmar con la clienta): horarios, dirección, WhatsApp, e-mail, barrios/tarifas de entrega, capacidad de áreas.

## Experiencia del cliente terminada

- Diseño responsive revisado a 320, 390, 768 y 1440 px, con fotos reales, botones animados, navegación por categorías y una barra inferior tipo app con iconos, sección activa y menú **Mais**. Cliente: Cardápio, Reservar, Minha visita, Pedido y Mais. Restaurante: Início, Pedidos, Reservas, Caixa y Mais (Clientes, Compras, Estoque, Equipe y Canais). En celular se ocultan las pestañas superiores; en escritorio se conserva la navegación habitual. Respeta movimiento reducido.
- **Reservas en tres pasos:** mesa (fecha, cantidad y área), horario y contacto. Atajos para hoy/mañana/sábado, resumen y validación. La confirmación aparece en **Minha visita** y en el panel.
- **Minha visita:** próximas reservas, reprogramación y cancelación, pedidos con seguimiento simulado y opción de repetirlos.
- **Detalle del producto:** foto cuando existe, precio real, cantidad, observación por ítem y acompañamientos opcionales de la misma carta. Las notas llegan al pedido y al panel.
- **Pedido en tres pasos:** productos y modalidad, entrega o retiro, contacto y pago de ejemplo. Muestra subtotal, tarifa y total antes de confirmar. No cobra ni envía nada.
- **Dos perfiles ficticios:** Fernanda (cliente frecuente, con reserva y pedido de ejemplo) y Marina (primera visita, sin actividad). Marina se incorpora al CRM al realizar su primera reserva o pedido. El selector permite probar ambos recorridos.
- **Roteiro:** guía de demostración con accesos a los escenarios y reinicio. Las herramientas de WhatsApp/e-mail y el avance manual del estado están agrupados como herramientas de demostración.

### Recorrido del cliente para revisar

1. En **Site do cliente**, tocar **Minha visita** para ver la reserva de Fernanda; probar **Alterar** o **Cancelar**.
2. Elegir **Marina · primeira visita** y reservar una mesa en tres pasos con **Usar exemplo**. Revisar el perfil creado en **Clientes** del panel.
3. Abrir un plato, cambiar su cantidad, agregar una observación y un acompañamiento; finalizar con entrega o retiro.
4. En el comprobante, abrir **Ferramentas da demonstração** para avanzar el pedido. El mismo pedido aparece en el panel y actualiza stock/caja una sola vez.
5. Desde **Minha visita → Pedidos**, repetir un pedido.
6. Abrir **Roteiro** y reiniciar para restaurar todos los ejemplos.

No ingresar datos personales reales: los contactos incluidos son ejemplos para la presentación. Cada visitante tiene una sesión independiente; los cambios se pierden al recargar y no se sincronizan entre dispositivos.

## Panel ampliado — demostración interactiva

Todos los datos operativos son ficticios y viven **solamente en memoria**. Se restauran al recargar la página o usar **Reiniciar demo**. No hay base de datos, integraciones bancarias, mensajes reales, autenticación del restaurante ni registros laborales reales. Los perfiles de acceso son ilustrativos.

- **Visão geral:** pendientes del día, entradas, próximas reservas, equipo y registro de acciones.
- **Clientes:** fichas creadas/actualizadas por reservas y pedidos, búsqueda por nombre/contacto, historial y preferencias. Coincidencias por teléfono o e-mail evitan duplicados.
- **Reservas e mesas:** mapa con capacidades de ejemplo, asignación de una o varias mesas, llegadas, cancelaciones, ausencias y lista de espera. Ocupación por horario.
- **Caixa e finanças:** entradas y salidas ficticias, filtros, caja en efectivo, conteo, diferencia de cierre y reapertura.
- **Compras:** proveedores, pedidos, recepción que suma stock y genera cuenta a pagar, pagos parciales que actualizan el libro de movimientos.
- **Estoque:** cantidades, mínimos, vencimientos de ejemplo, ajustes, pérdidas y fichas técnicas ilustrativas. Aceptar un pedido descuenta sus ingredientes una vez; concluirlo registra el ingreso una vez.
- **Equipe:** altas/edición de personas, escala semanal, turnos nocturnos, pausas, detección de superposiciones y marcación simulada de inicio/fin.
- **Canais:** se conserva la vista de WhatsApp, Instagram y e-mail, todos señalados como simulaciones.

### Recorrido sugerido para presentar
1. Abrir `index.html` y elegir **Painel do restaurante**.
2. En **Visão geral**, tocar **Simular nova reserva** y buscar a Fernanda en **Clientes**.
3. En **Compras**, recibir PC-104 y revisar el aumento de pescado en **Estoque**.
4. Registrar un pago parcial y comprobar la salida en **Caixa e finanças**.
5. Crear un turno en **Equipe** y probar un horario superpuesto.
6. Hacer un pedido desde el sitio del cliente, aceptarlo en el panel y concluirlo para ver stock, cliente y finanzas actualizados.
7. Usar **Reiniciar demo** para volver al punto de partida.

El cardápio y sus precios reales se mantienen. Proveedores, empleados, costos, cantidades, recetas y registros financieros son ejemplos para la presentación. Se conserva HTML/CSS/JS vanilla, sin build ni dependencias nuevas.




## Aviso manual de retirada pelo WhatsApp — demo

Em **Painel → Pedidos**, um pedido de **Retirada** ganha o botão **Avisar pelo WhatsApp** quando estiver pronto. O operador confere o número do cliente, escolhe balcão ou restaurante, vê a mensagem com o código do pedido e usa **Simular envio do aviso**. O registro aparece no cartão, no histórico de Canais e no comprovante do cliente. Não envia mensagens, não abre o WhatsApp e não registra cobrança nem nova baixa de estoque.

Para testar com os exemplos: aceitar o pedido #0428, marcar como pronto e usar o botão de aviso. Depois usar **Marcar retirado** para concluir. O mesmo aviso funciona para pedidos de retirada feitos antecipadamente. Um reenvio exige reabrir a prévia e confirmar novamente; submissões repetidas da mesma prévia não duplicam o aviso. Recarregar ou reiniciar a demo restaura os dados iniciais.


## Botones y tiempos de preparación editables — demo

- Botones con jerarquía óxido/marino, relieve, respuesta al pulsar, foco visible y movimiento reducido. Las acciones de WhatsApp usan un SVG local compartido de Bootstrap Icons; su licencia está en `assets/THIRD-PARTY-NOTICES.txt`. No se añadió ninguna biblioteca ni proceso de build.
- Cada artículo de la carta muestra un tiempo de preparación **ficticio**. En **Painel → Pedidos → Tempos da carta** se editan todos los artículos y el desplazamiento adicional de entrega.
- Los productos se preparan en paralelo: la previsión del carrito usa el **mayor tiempo de preparación** entre sus artículos. Para entrega suma el desplazamiento configurado; para retirada no. Las cantidades no se suman como tiempos secuenciales. Si el volumen requiere más espera, la persona operadora ajusta el pedido.
- Cada pedido recibido guarda una copia de sus tiempos y su hora prevista. Editar los tiempos de la carta afecta al carrito y a los nuevos pedidos; conserva las previsiones de los pedidos ya recibidos.
- En la tarjeta de cada pedido pendiente, **Ajustar previsão** permite indicar los minutos restantes **a partir de ahora**, con atajos de +10/+20/+30 minutos y motivo visible al cliente, por ejemplo **Alta demanda**. Para entrega ese nuevo plazo ya incluye el desplazamiento; no se vuelve a sumar.
- La previsión y sus ajustes aparecen en **Minha visita** dentro de la misma sesión. Un plazo vencido pide actualización: nunca marca el pedido listo automáticamente. Al estar listo para retirar se conserva el aviso manual de WhatsApp.
- Ajustar tiempos no cobra, no cambia el estado del pedido y no descuenta ingredientes. En la demo no hay sincronización entre dispositivos ni mensajes reales; recargar o reiniciar restaura los ejemplos.

### Recorrido para revisar

1. En **Pedidos → Tempos da carta**, cambiar el tartar de 18 a 30 minutos y guardar.
2. En el sitio del cliente, agregar tartar y una cerveza: retirada calcula 30 minutos; entrega suma el desplazamiento ficticio configurado. Confirmar el pedido y abrir su comprobante.
3. Volver a **Pedidos**, usar **Ajustar previsão**, indicar 60 minutos con motivo **Alta demanda** y guardar.
4. En **Minha visita → Pedidos**, comprobar el nuevo plazo y el aviso de actualización de la equipe.
5. Cambiar otra vez el tiempo del tartar y comprobar que la previsión del pedido anterior se mantiene.
