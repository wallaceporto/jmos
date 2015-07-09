# Preguntas de Uso Frecuente (PUF o FAQ) #

## General ##

#### ¿Qué es jMOS? ####
jMOS es una librería de código abierto fácil de utilizar para trabajar con los sistemas informáticos de Newsroom (NCS) y Media Object Servers (MOS) sobre la plataforma de Java usando los rápidos motores de procesamiento de XML sobre streaming como SAX, JAXP y StAX.

#### ¿Qué es la licencia Apache? ####
Utilizamos una licencia de código fuente abierta Apache. Esto significa, en la práctica, que usted puede hacer casi cualquier cosa que usted desea con el código, incluyendo su uso en software comercial.

#### ¿Qué necesito agregar a mi CLASSPATH? ####
La librería jMOS.jar solo contiene las clases de jMOS, tienes que incluir las clases de SAX y el parse de SAX que elijas en tu CLASSPATH, también tienes que incluir el StAX, Logger y ara-utils.jar en tu CLASSPATH.

#### ¿Como notifico un bug? ####
El tracker ayuda a mantener los bus reportados en un sitio. Siga los siguientes pasos para añadir un nuevo bug:
  1. Preguntate si realmente es un bug. Es quizá algún problema de configuración o del hardware, etc.
  1. Busca en los bugs reportados problemas similares. Si está ya allí, añada otro comentario, en vez de agregar un bug similar.
  1. Si usted no ha encontrado un bug existente sobre su problema, considere agregar un nuevo ticket del bug.
  1. Elija un asunto, componente, versión, etc.
  1. Describa el problema, intentando proporcionar bastante información para que sea posible reproducir el bug.

#### ¿Como envio un parche? ####
Los parches se deben enviar vía tracker. Cree un ticket del bug o solicitud de mejora y añada su archivo del parche.

## Protocolo MOS ##

#### ¿Que perfiles estan soportados? ####
Perfiles 0, 1 y 2.

## Usando jMOS ##

#### ¿Como cambio el parse de SAX por defecto? ####
Tienes que cambiar la propiedad de sistema javax.xml.parsers.SAXParserFactory antes de llamar a cualquier metodo estatico de la clase Server.
  * Ejemplo 1:
    * Para el parse xml de Crimson: System.setProperty("javax.xml.parsers.SAXParserFactory", "org.apache.crimson.jaxp.SAXParserFactoryImpl");
    * Para el parse xml de Xerces: System.setProperty("javax.xml.parsers.SAXParserFactory", "org.apache.xerces.jaxp.SAXParserFactoryImpl");
  * Ejemplo 2:
    * Para el parse xml de Crimson: javac -Djavax.xml.parsers.SAXParserFactory=org.apache.crimson.jaxp.SAXParserFactoryImpl
    * Para el parse xml de Xerces: javac -Djavax.xml.parsers.SAXParserFactory=org.apache.xerces.jaxp.SAXParserFactoryImpl

#### ¿Como cambio el manejado de escritura de StAX por defecto? ####
Tienes que cambiar la propiedad de sistema javax.xml.stream.XMLOutputFactory antes de llamar a cualquier metodo estatico de la clase Server.
  * Ejemplo 1:
    * Para el parse xml de Bea: System.setProperty("javax.xml.stream.XMLOutputFactory", "com.bea.xml.stream.MXParserFactory");
    * Para el parse xml de WebLogic: System.setProperty("javax.xml.stream.XMLOutputFactory", "weblogic.xml.stax.XMLStreamOutputFactory");
  * Ejemplo 2:
    * Para el parse xml de Bea: javac -Djavax.xml.stream.XMLOutputFactory=com.bea.xml.stream.MXParserFactory
    * Para el parse xml de WebLogic: javac -Djavax.xml.stream.XMLOutputFactory=weblogic.xml.stax.XMLStreamOutputFactory