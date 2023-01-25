 
# Actividad 1  201903767

### Tipos de kernel y sus diferencias


#### Monolítico

Este tipo de kernel tiene todas las funciones del sistema operativo juntas en un solo módulo de código. Es el tipo de kernel **más antiguo** y es utilizado en sistemas operativos como Unix y Linux.

#### Microkernel

Este tipo de kernel tiene **solo las funciones esenciales** del sistema operativo en el núcleo, y las funciones adicionales se ejecutan en servidores separados. Es más pequeño y más seguro que el kernel monolítico, pero también es más lento debido a la comunicación entre los servidores.

#### Hybrid kernel

Este tipo de kernel **combina** las características de ambos tipos de kernel anterior, tiene un núcleo pequeño y esencial, pero también tiene algunas funciones adicionales en el núcleo. Este tipo de kernel es utilizado en sistemas operativos como Windows NT.

#### Exokernel

Este tipo de kernel es una nueva tendencia en la investigación, su objetivo es proveer una interfaz minimalista para que los usuarios y los sistemas puedan acceder directamente a los recursos del sistema.

### User vs Kernel Mode

#### User mode

Este es el nivel de acceso que utilizan los programas y aplicaciones que ejecutan los usuarios. El modo usuario no tiene acceso directo a los recursos del sistema, como la memoria y los dispositivos de entrada/salida. En cambio, tiene que solicitar acceso a estos recursos a través de funciones y llamadas del sistema. El objetivo de este modo es asegurar que los programas no puedan dañar accidentalmente el sistema.

#### Kernel Mode

Este es el nivel de acceso utilizado por el sistema operativo y los controladores de dispositivos. El modo kernel tiene acceso completo a todos los recursos del sistema y puede realizar operaciones críticas, como gestionar la memoria y controlar los dispositivos. El objetivo de este modo es permitir al sistema operativo controlar y proteger el sistema.
