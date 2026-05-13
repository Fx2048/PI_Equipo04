

# Informe Técnico – Configuración MQTT  en SenseCraft AI con XIAO

## Proyecto

Implementación de comunicación MQTT utilizando SenseCraft AI y dispositivos XIAO para transmisión de datos IoT.

## Referencias

* Repositorio del proyecto: [https://github.com/Fx2048/PI_Equipo04/tree/main/Recursos/Imagenes/mqtt_success](https://github.com/Fx2048/PI_Equipo04/tree/main/Recursos/Imagenes/mqtt_success)
* Documentación base utilizada: [https://wiki.seeedstudio.com/sensecraft-ai/tutorials/sensecraft-ai-output-mqtt-xiao/](https://wiki.seeedstudio.com/sensecraft-ai/tutorials/sensecraft-ai-output-mqtt-xiao/)

---

# 1. Introducción

El presente informe documenta el proceso de configuración e integración del protocolo MQTT utilizando la plataforma SenseCraft AI y dispositivos XIAO. El objetivo inicial era lograr una comunicación exitosa entre el dispositivo IoT y un broker MQTT, siguiendo la guía oficial proporcionada por Seeed Studio.

Sin embargo, durante el desarrollo y validación del sistema no se logró establecer una conexión funcional con el broker MQTT. En lugar de obtener la transmisión correcta de datos y la sincronización esperada, únicamente se alcanzó una configuración parcial y fallida.

Este documento recopila las evidencias gráficas obtenidas durante el proceso, analiza los posibles errores detectados y explica el comportamiento observado en la plataforma.

---

# 2. Objetivo

## Objetivo General

Implementar un sistema de comunicación MQTT utilizando SenseCraft AI y dispositivos XIAO para el envío de datos IoT.

## Objetivos Específicos

* Configurar correctamente los parámetros de red Wi‑Fi.
* Establecer comunicación con un broker MQTT.
* Validar la transmisión de datos desde el dispositivo.
* Analizar errores de conexión y configuración.
* Comparar el resultado esperado con el resultado obtenido.

---

# 3. Arquitectura Esperada

Según la documentación oficial de Seeed Studio, el sistema debía funcionar bajo la siguiente arquitectura:

1. El dispositivo XIAO se conecta a una red Wi‑Fi.
2. SenseCraft AI inicializa el flujo MQTT.
3. El broker MQTT recibe las credenciales.
4. El dispositivo publica mensajes en un tópico definido.
5. El servidor o cliente MQTT recibe correctamente los datos.

---

# 4. Archivos Analizados

Durante las pruebas se generaron múltiples capturas y evidencias del sistema.

| Archivo              | Descripción Referencial                   |
| -------------------- | ----------------------------------------- |
| `configuracion.png`  | Configuración inicial del sistema MQTT    |
| `configuraciona.png` | Parámetros avanzados de configuración     |
| `consola.png`        | Salida de consola durante la ejecución    |
| `consolab.png`       | Errores adicionales mostrados en consola  |
| `gorra.png`          | Evidencia física del prototipo            |
| `interface.png`      | Interfaz principal de configuración       |
| `interfacea.png`     | Configuración secundaria de interfaz      |
| `interfaceaa.png`    | Ajustes adicionales del sistema           |
| `interfaceb.png`     | Vista alternativa de configuración        |
| `logs.png`           | Registros de errores y eventos            |
| `modelo.png`         | Modelo del flujo de comunicación esperado |
| `modelo1.png`        | Variación o ajuste del modelo inicial     |
| `mqtt.png`           | Configuración del broker MQTT             |
| `silla.png`          | Evidencia física del entorno de pruebas   |
| `silla2.png`         | Evidencia complementaria del entorno      |

---

# 5. Configuración Realizada

## Parámetros Wi‑Fi

Se configuró una red inalámbrica para permitir la conexión del dispositivo al entorno de pruebas.

### Datos utilizados

* SSID configurado
* Contraseña de acceso
* Tipo de cifrado automático (AUTO)

## Parámetros MQTT

Se intentó configurar:

* Host MQTT
* Puerto MQTT
* Client ID
* Usuario
* Contraseña
* SSL deshabilitado
* Flujo personalizado MQTT

No obstante, el sistema mostraba mensajes indicando que ciertos parámetros eran requeridos o inválidos.

---

# 6. Resultado Esperado

De acuerdo con la guía oficial de Seeed Studio, se esperaba:

* Conexión exitosa al broker MQTT.
* Publicación automática de datos.
* Confirmación de conexión en consola.
* Comunicación estable entre dispositivo y servidor.
* Visualización de mensajes MQTT en tiempo real.

---

# 7. Resultado Obtenido

El resultado obtenido fue una configuración fallida.

Las observaciones fueron las siguientes:

* El sistema no estableció conexión con el broker MQTT.
* No se generó transmisión de datos.
* La consola mostró errores relacionados con host y puerto.
* El flujo MQTT no llegó al estado operativo.
* La plataforma permaneció únicamente en etapa de configuración.
* No hubo confirmación de autenticación exitosa.

---

# 8. Evidencias del Fallo

## 8.1 Configuración MQTT

Las imágenes `configuracion.png`, `configuraciona.png` y `mqtt.png` muestran el proceso de ingreso de parámetros MQTT.

Se observan mensajes indicando:

* `mqtt.host is required`
* `mqtt.port is required`
* Solicitud obligatoria de contraseña

Esto evidencia que el sistema no validó correctamente la configuración ingresada o que algunos campos no fueron aceptados por la plataforma.

---

## 8.2 Consola del Sistema

Las capturas `consola.png`, `consolab.png` y `logs.png` contienen información relacionada con errores de ejecución.

Entre los problemas identificados destacan:

* Fallos de autenticación.
* Problemas de inicialización MQTT.
* Posibles errores de conexión de red.
* Ausencia de handshake con el broker.

---

## 8.3 Interfaz del Sistema

Las imágenes:

* `interface.png`
* `interfacea.png`
* `interfaceaa.png`
* `interfaceb.png`

muestran el comportamiento de la plataforma durante el intento de configuración.

Se aprecia que el flujo no alcanzó el estado de conexión exitosa esperado por la documentación oficial.

---

## 8.4 Modelo Esperado

Las imágenes `modelo.png` y `modelo1.png` representan el modelo esperado de funcionamiento del sistema.

La intención era lograr:

* Recepción de datos.
* Publicación MQTT.
* Integración IoT funcional.
* Flujo automatizado de comunicación.

Sin embargo, el sistema nunca llegó a completar dicha arquitectura funcional.

---

# 9. Posibles Causas del Problema

A partir del análisis realizado, se identifican las siguientes posibles causas:

## 9.1 Configuración Incorrecta del Broker

El host o puerto MQTT podrían haber sido incorrectos o incompatibles con la plataforma utilizada.

## 9.2 Problemas de Compatibilidad

Puede existir incompatibilidad entre la versión de SenseCraft AI y el broker MQTT seleccionado.

## 9.3 Credenciales Inválidas

La autenticación MQTT pudo haber fallado debido a:

* Usuario incorrecto.
* Contraseña incorrecta.
* Client ID inválido.

## 9.4 Restricciones de Red

La red Wi‑Fi utilizada pudo bloquear:

* Puertos MQTT.
* Resolución DNS.
* Comunicación externa.

## 9.5 Configuración SSL

La habilitación o deshabilitación incorrecta de SSL pudo impedir la conexión.

---

# 10. Comparación entre Resultado Esperado y Resultado Real

| Aspecto              | Resultado Esperado | Resultado Obtenido |
| -------------------- | ------------------ | ------------------ |
| Conexión Wi‑Fi       | Exitosa            | Parcial            |
| Conexión MQTT        | Exitosa            | Fallida            |
| Publicación de datos | Activa             | No realizada       |
| Validación de host   | Correcta           | Error              |
| Validación de puerto | Correcta           | Error              |
| Flujo MQTT           | Operativo          | Incompleto         |
| Comunicación IoT     | Funcional          | No funcional       |

---

# 11. Conclusiones

* No se logró establecer una comunicación MQTT funcional.
* La configuración quedó incompleta debido a errores de validación y conexión.
* El sistema no pudo publicar datos hacia el broker MQTT.
* Las evidencias muestran que el problema se presentó principalmente durante la configuración del host y puerto MQTT.
* El flujo de comunicación esperado por la documentación oficial no pudo completarse.

---

# 12. Recomendaciones

Para futuras pruebas se recomienda:

1. Verificar nuevamente el broker MQTT utilizado.
2. Validar credenciales y puertos manualmente.
3. Probar brokers públicos compatibles.
4. Revisar compatibilidad de versiones de SenseCraft AI.
5. Utilizar herramientas de diagnóstico MQTT como MQTT Explorer o Mosquitto.
6. Confirmar que la red permita tráfico MQTT.
7. Realizar pruebas locales antes de usar servicios externos.

---

# 13. Referencias Bibliográficas

## Documentación Oficial

Seeed Studio. “SenseCraft AI Output MQTT XIAO Tutorial”. Disponible en:
[https://wiki.seeedstudio.com/sensecraft-ai/tutorials/sensecraft-ai-output-mqtt-xiao/](https://wiki.seeedstudio.com/sensecraft-ai/tutorials/sensecraft-ai-output-mqtt-xiao/)

## Repositorio del Proyecto

Repositorio de evidencias y capturas:
[https://github.com/Fx2048/PI_Equipo04/tree/main/Recursos/Imagenes/mqtt_success](https://github.com/Fx2048/PI_Equipo04/tree/main/Recursos/Imagenes/mqtt_success)

---

# 14. Anexos

## Anexo A – Capturas de Configuración

### configuracion.png

![configuracion](https://raw.githubusercontent.com/Fx2048/PI_Equipo04/main/Recursos/Imagenes/mqtt_success/configuracion.png)

### configuraciona.png

![configuraciona](https://raw.githubusercontent.com/Fx2048/PI_Equipo04/main/Recursos/Imagenes/mqtt_success/configuraciona.png)

### mqtt.png

![mqtt](https://raw.githubusercontent.com/Fx2048/PI_Equipo04/main/Recursos/Imagenes/mqtt_success/mqtt.png)

---

## Anexo B – Capturas de Consola

### consola.png

![consola](https://raw.githubusercontent.com/Fx2048/PI_Equipo04/main/Recursos/Imagenes/mqtt_success/consola.png)

### consolab.png

![consolab](https://raw.githubusercontent.com/Fx2048/PI_Equipo04/main/Recursos/Imagenes/mqtt_success/consolab.png)

### logs.png

![logs](https://raw.githubusercontent.com/Fx2048/PI_Equipo04/main/Recursos/Imagenes/mqtt_success/logs.png)

---

## Anexo C – Interfaces del Sistema

### interface.png

![interface](https://raw.githubusercontent.com/Fx2048/PI_Equipo04/main/Recursos/Imagenes/mqtt_success/interface.png)

### interfacea.png

![interfacea](https://raw.githubusercontent.com/Fx2048/PI_Equipo04/main/Recursos/Imagenes/mqtt_success/interfacea.png)

### interfaceaa.png

![interfaceaa](https://raw.githubusercontent.com/Fx2048/PI_Equipo04/main/Recursos/Imagenes/mqtt_success/interfaceaa.png)

### interfaceb.png

![interfaceb](https://raw.githubusercontent.com/Fx2048/PI_Equipo04/main/Recursos/Imagenes/mqtt_success/interfaceb.png)

---

## Anexo D – Modelos y Evidencias

### modelo.png

![modelo](https://raw.githubusercontent.com/Fx2048/PI_Equipo04/main/Recursos/Imagenes/mqtt_success/modelo.png)

### modelo1.png

![modelo1](https://raw.githubusercontent.com/Fx2048/PI_Equipo04/main/Recursos/Imagenes/mqtt_success/modelo1.png)

### gorra.png

![gorra](https://raw.githubusercontent.com/Fx2048/PI_Equipo04/main/Recursos/Imagenes/mqtt_success/gorra.png)

### silla.png

![silla](https://raw.githubusercontent.com/Fx2048/PI_Equipo04/main/Recursos/Imagenes/mqtt_success/silla.png)

### silla2.png

![silla2](https://raw.githubusercontent.com/Fx2048/PI_Equipo04/main/Recursos/Imagenes/mqtt_success/silla2.png)

---

# Referencias Visuales Utilizadas

Repositorio principal:

[https://github.com/Fx2048/PI_Equipo04/tree/main/Recursos/Imagenes/mqtt_success](https://github.com/Fx2048/PI_Equipo04/tree/main/Recursos/Imagenes/mqtt_success)

Documentación oficial:

[https://wiki.seeedstudio.com/sensecraft-ai/tutorials/sensecraft-ai-output-mqtt-xiao/](https://wiki.seeedstudio.com/sensecraft-ai/tutorials/sensecraft-ai-output-mqtt-xiao/)

