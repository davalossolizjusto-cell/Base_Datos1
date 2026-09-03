Paso 1: Recoger la narración del cliente Actores:
       Entrevista a la señora Lupe Barrionuevo (Restaurante o Pension propio)
              -La señora se encuentra en la nesecidad de mejorar su sistema de pedidos, ya que el pricipal problema que ella tiene es la gran cantidad de pedidos que le llegan 
               al momento mas concurrido (hora del almuerzo) al tratar de sobrellevar la mayoria de los pedidos pudo observar que algunos pedidos no cumplian con ciertos puntos,
               los cuales le hacian perder dinero y el prducto en algunos casos este seria el hecho de que la persona que hacia el pedido no completaba o no enviaba la direccion
               a la cual se debia de entregar los pedidos y tambien en algunos casos los comprobantes de pago no se llegaban a verificar a tiempo.
              -El negocio funciona principalmente a base de vender comida, recibir pedidos ya sean para que les llegue a casa o ser recogidos por ellos mismos los metodos de pago
               son via efectivo(en persona), y transferencia o pago por qr.
              -Los pedidos principalmente son gestionados por la misma persona o algun ayudante(recepcion), tambien cuenta con conductores con sus propios vehiculos(motos)para 
               hacer las entregas o envios.

 

Paso 2: Identificar entidades y atributos

Cliente:  nombre, apellido, telefono, direccion.
Restaurante: nombre,direccion,telefono.
Repartidor: nombre, id_repatidor, CI, telefono.
Personal(Recepcionista):  nombre, id_recepcion,CI, telefono.



Paso 3: Determinar claves primarias y tipos básicos
Cliente: Direccion (String, PK).
Restaurante: Direccion(String, Pk).
Repartidor: id_repartidor(INT, Pk) CI(VARCHAR, Unique).
Personal(Recepcionista): id_recepcionista(INT, Pk) CI(VARCHAR, Unique).


Paso 4: Detectar relaciones y cardinalidades (Justificadas)
Cliente N:M Pedido 
   justificacion un cliente puede hacer muchos pedidos y un pedido puede ser hecho por muchos clientes.

Pedido N:M Recepcionista
   justificacion un pedido puede ser reservado por diferentes recepcionistas y un recepcionista puede recivir muchos pedidos. 

Reserva 1:M Recepcionista
   justificacion Una reserva pueden ser hechas por diferentes recepcionistas pero un recepcionista solo puede hacer una reserva.

Restaurante 1:M Reserva
   justificacion un restaurante puede registrar muchas reservas pero las reservas solo puedes ser registradas en ese restaurante.

Restaurante 1:M Envio
   justificacion Un restaurante puede hacer muchos envios, pero en este contexto los envios solo pueden ser realizados por ese restaurante.

Envio N:M Repartidor
  justificacion un Envio puede ser realizado por muchos repartidores y un repartidor puede hacer muchos envios.

Repartidor N:M Entrega
 justificacion un repartidor puede hacer muchas entregas y una entrega puede ser hecha por diferentes repartidores.

Entrega N:M Cliente
 justificacion una Entrega puede tener diferentes clientes y un cliente puede recibir muchas entregas.


Paso 5: Restricciones importantes

Unicidad (UNIQUE): El telefono del cliente es necesario para la reserva.

No nulos (NOT NULL):
Direccion el cliente nesecita si o si dar la ubicacion del pedido.

Restricciones de verificación (CHECK):
estado en Reserva debe restringirse a valores válidos: ('Pendiente', 'Completada', 'Cancelada').
monto en Pagos debe ser mayor a 0 (monto > 0).





Paso 6: Representación del DER (Notación Crow's Foot - Resumen Estructural)

Paso 7: Mapeo a Tablas Relacionales (Esquema Físico)
