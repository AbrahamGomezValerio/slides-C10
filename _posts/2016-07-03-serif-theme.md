---
title: "Detección de errores y corrección"
layout: post
permalink: /deteccion-correccion/
theme: moon

slides:
  - title: "Nombre"
    slide-data: "Abraham Alejandro Gómez Valerio\nTema: Detección de errores y corrección\nMétodo: RevealJS y Slides"

  - title: "Introducción"
    slide-data: "Las redes deben ser capaces de transferir datos de un dispositivo a otro con una buena precisión. La mayoría de aplicaciones deben garantizar que los datos recibidos sean iguales a los transmitidos. Cada vez que se transmiten datos pueden existir errores o que se corrompan los datos, por ello requieren de un mecanismo para detectar y corregir errores."

  - title: "Tipos de errores"
    slide-data: "Cada vez que los bits de información se transfieren de un punto a otro, pueden sufrir interferencias. Esto provoca que puedan cambiar la forma de la señal que se vaya a recibir. Un solo error de un bit puede cambiar un 0 a un 1 o viceversa, incluso llegando a cambiar varios bits."

  - title: "Errores Comunes"
    slide-data: "• <b>Error de un solo bit:</b> Se trata cuando un solo bit de una cantidad de datos se cambia de un 0 a un 1 o de un 1 a un 0.\n• <b>Error en ráfaga:</b> Sucede cuando dos o más bits en la unidad de datos cambian de 0 a 1 o viceversa, afectando a más bits."

  - title: "Redundancia"
    slide-data: "El concepto central de detectar o corregir errores es la redundancia. Para detectar o corregir errores, se necesitan enviar bits extra junto a nuestros datos. Esta redundancia es eliminada por el receptor, permitiendo detectar o corregir los bits corruptos."

  - title: "¿Corregir o Detectar?"
    slide-data: "La corrección de errores es más difícil que la detección.\n• <b>Detección de errores:</b> Solo observa si ha ocurrido un error, no interesa el número de errores.\n• <b>Corrección de errores:</b> Se necesita saber el número exacto de bits corruptos y su localización."

  - title: "Métodos de corrección"
    slide-data: "Existen 2 métodos de corrección de errores:\n• <b>Forward error correction:</b> El receptor intenta adivinar el mensaje usando los bits restantes.\n• <b>Retransmisión:</b> El receptor pide al emisor reenviar el mensaje hasta que llegue sin errores."

  - title: "Codificar"
    slide-data: "La redundancia ha adquirido varios esquemas de código. El emisor añade redundancia a los bits mientras un proceso crea una relación entre los bits redundantes y los bits verdaderos detectados."

  - title: "Codificación por bloques"
    slide-data: "En la codificación por bloques, dividimos nuestro mensaje en bloques, cada uno con 'K' cantidad de bits llamada 'Palabra'. Se añaden 'r' bits redundantes para crear una longitud 'n = k + r'."

  - title: "Detección de errores"
    slide-data: "Existen maneras de detectar errores usando la codificación por bloques.\n1. El receptor encuentra la lista de los 'Códigos' válidos.\n2. El 'Código' original ha sido cambiado a uno inválido."

  - title: "Corrección de errores"
    slide-data: "En una corrección de errores, el receptor necesita saber que un solo 'código' es inválido. Por ello, necesita encontrar (o adivinar) el 'código' original enviado."

  - title: "Hamming Distance"
    slide-data: "La Hamming distance entre 2 'Palabras' (del mismo tamaño) es el número de diferencias entre sus bits. Se encuentra usando un operador de XOR y contando el número de 1s en el resultado."

  - title: "Código de bloques lineales"
    slide-data: "Casi todos los bloques de códigos usan un subconjunto llamado Código de bloques lineales. Los bloques no lineales hacen más difícil la detección y corrección de errores."

  - title: "Códigos cíclicos"
    slide-data: "Los códigos cíclicos son un tipo de Código de bloques con una propiedad extra. Si un 'Código' es rotado o sus dígitos se ponen al revés, el resultado será otro 'Código' diferente."

  - title: "Implementación en el Hardware"
    slide-data: "Una ventaja de los códigos cíclicos es que el codificador y el decodificador pueden ser fácilmente implementados en hardware. Sin embargo, esto incrementa el ratio de verificación de bits."

  - title: "Ventajas de los códigos cíclicos"
    slide-data: "Los códigos cíclicos son buenos para:\n• Detectar errores de 1 bit, errores dobles, errores impares y errores de ráfaga.\n• Implementarse fácilmente en hardware y software."

  - title: "Checksum"
    slide-data: "El último tipo de detector de errores es el CHECKSUM. Se basa en la redundancia y es utilizado por diversos protocolos de Internet para la detección de errores."

  - title: "Uso del Checksum"
    slide-data: "La aplicación del Checksum consiste en enviar los bits al receptor junto con la suma de los bits dentro del paquete, permitiendo al receptor comparar el resultado."

  - title: "Checksum en el Internet"
    slide-data: "El Internet utiliza un checksum de 16 bits. El receptor calcula el resultado al dividir el mensaje en palabras de 16 bits y sumarlas usando complemento a uno."

  - title: "Detección de errores con Checksum"
    slide-data: "El receptor puede usar los siguientes pasos para detectar errores:\n1. El mensaje (incluido el checksum) se divide en palabras de 16 bits.\n2. Se suman las palabras, incluyendo 1 más.\n3. La suma es complementada y se convierte en el nuevo checksum.\n4. Si el checksum es 0, el mensaje es aceptado; de lo contrario, será rechazado."

---

{% for slide in page.slides %}
                    
<section data-background="{% if slide.background %}{{slide.background}}{% else %}{{page.background}}{% endif %}"><h1>{{slide.title}}</h1>{{ slide.slide-data }}</section>
                    
{% endfor %}
    
