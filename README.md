# Negocio: Mesa de Ayuda de Empresa de Servicios
Este proyecto documenta el diseño completo de un sistema utilizando UML, abordando cada etapa del modelado para resolver problemas concretos de información en un contexto de negocio específico.

Instrucción de uso: Seleccione  _**negocio.rar,**_  posteriormente download raw file, se descargará un archivo rar comprimido con una carpeta con los artefactos en formato pdf para facilitar sus visualización.

Este repositorio contiene el diseño completo de un sistema utilizando teoría de UML, desarrollado como parte de una ejercitación académica para modelar soluciones a problemas de información en contextos concretos de negocio. Incluye:

-   Modelo de Requisitos: Identificación de actores y casos de uso que permiten modelar una solución integral al problema planteado, junto con diagramas de casos de uso.
-   Especificaciones Detalladas: Documentación exhaustiva de los casos de uso mediante descripciones de flujo de sucesos, diagramas de transición de estados, y diseños de interfaces de usuario que contemplan los parámetros de entrada.
-   Diagrama de Clases: Desarrollo de un modelo de dominio que permite sostener la funcionalidad de los casos de uso, integrando conceptos de clases, atributos, relaciones, navegabilidad y multiplicidad.
-   Decisiones de Diseño: Registro de las decisiones tomadas para implementar la solución diseñada, con análisis comparativo de alternativas en términos de ventajas, restricciones y desventajas.
-   Integración de Artefactos: Aplicación de herramientas como el modelo del dominio y el diseño de la interfaz de usuario para lograr una especificación detallada y consistente.

Este proyecto refleja un enfoque sistemático y detallado, orientado a comprender y resolver problemas a través de la especificación de requerimientos y la construcción de modelos UML.

A continuación, se presenta el texto que corresponde a la definición inicial de requisitos para el sistema en cuestión.

> “Una empresa de servicios, nos ha encargado automatizar su sistema de mesa de ayuda para una mejor agilidad en la atención. Es vital para ellos el registro en tiempo y forma de los avances en la solución de los casos dado que el ente regulador del servicio, ERE, aplica multas por la falta de cumplimiento. Cuando un operador atiende una llamada de un cliente, lo primero que solicita es el número de cliente para verificar que esté registrado. Todas las validaciones correspondientes a la existencia y estado de los clientes se realiza mediante comunicación vía servicios web con el sistema de ventas principal de la empresa. Mediante la interacción con el cliente durante la llamada, surge la determinación del tipo de caso de acuerdo a la interpretación, que hace el operador, del problema descripto por el cliente. Cada tipo de caso tiene configurados en el sistema, el conjunto de instancias posibles que están previstas para su solución. Cada instancia tiene definida qué sector de la empresa debe ocuparse de la misma y el tiempo máximo de resolución/terminación establecido para la instancia. Las instancias deben interpretarse como intentos de solución. Queriendo decir esto que si el caso queda resuelto en la instancia n, no es necesario continuar con la instancia n+1 y siguientes. El primer paso/instancia prevista “siempre” para cualquier tipo de caso, es la atención telefónica que hace el mismo operador. De esta atención primaria podría determinarse que el caso puede cerrarse y en tal situación, no debieran quedar pendientes de ejecución el resto de las instancias predefinidas para el tipo de caso. Los especialistas pertenecientes a cada sector, revisan permanentemente su bandeja de trabajo, la cual se alimenta de aquellos casos que caen en la órbita de su sector pero que aún no han sido “tomados” por un especialista concreto. Cada especialista puede tomar cualquier caso pendiente que visualiza para darle tratamiento. Pero una vez que ha sido tomado por un especialista puntual, el sistema ya no permite a otro especialista del sector ponerse a trabajar con el mismo caso. Mientras el plazo previsto para la atención en el sector no caduque, el especialista puede ir registrando sus tareas, avances, comunicaciones internas y externas para hacer evolucionar el caso en la instancia actual. Estas tareas puntuales para cada instancia, están clasificadas en un nomenclador para conocer su naturaleza. Pero la cantidad, características y secuencia de las mismas no están regladas y se administra a criterio del especialista. Cuando el especialista da por terminado su trabajo, registrará el resultado de la instancia a su cargo. Esto es fundamental porque si consigna el estado “Resuelto”, en el resto de las instancias previstas deben anularse y debe darse por finalizado el caso. En cambio, si no se pudo solucionar el caso con la instancia a su cargo, deberá consignar “Sin resolver”, con lo que automáticamente el caso quedará disponible para que algún especialista asignado al sector responsable de la instancia n+1 pueda tomar el caso y continuar con el mismo. Se entiende que esta definición podrá ser realizada por el especialista dentro del plazo de caducidad de la instancia. De alcanzarse la caducidad el sistema deberá accionar automáticamente activando la siguiente instancia. Si la última instancia prevista para el tipo de caso se alcanzara con resultado “Sin Resolver” el sistema automáticamente generará otro caso relacionado al anterior con todas las instancias previstas para el tipo de caso. La fecha de inicio para la primera instancia, en caso de iteraciones, es la fecha de cierre del caso/iteración anterior. Por cada iteración que se suma a un caso, los tiempos máximos de finalización de cada instancia se restringe dado que el ERE ejerce más presión sobre la empresa para solucionar el inconveniente. Esto está parametrizado así como también la máxima cantidad de insistencias permitidas por caso para cada tipo de caso. Debe preverse una salida para que el ERE consulte por fecha desde hasta: nro. caso, descripción, fecha de ingreso del caso, cliente, estado del caso, días ejecutados, días previstos, cantidad de iteraciones del caso.” Debemos atender a los siguientes trabajos de diseño que nos delega, el analista de sistemas líder a. El analista de sistemas líder revisa los artefactos entregados donde hemos plasmado la arquitectura diseñada hasta el momento y recomienda modificar el diseño alrededor de la configuración de tipos de instancias para cada tipo de caso, señalándonos que el modelo de datos resultante no es óptimo para la administración de los cambios de configuración en el tiempo. Nos pide evitar modelar de mejor manera las fechas de vigencia de la configuración de cada tipo de caso, dado que los cambios no son realizados sobre un tipo de instancia particular en una fecha arbitraria sino que se modifica todo el circuito en una fecha dada. El modelo no muestra la solidez necesaria para evitar cargas inconsistencias o con fechas descontroladas. Alcance Actividad 4 según guía: Caso de Uso Tomar Caso
