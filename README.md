<p align="center"><img src="https://github.com/Computacion-UNL/tw_violencia_genero/assets/50312849/45e7fb99-ee29-435f-9570-d0ff67b985ac"/></p> 

## Tabla de contenidos:
---
- [Autor](#autor)
- [Introducción](#introducción)
- [Desarrollo:](#desarrollo)
  - [Construcción del conjunto de datos proveniente de la red social Twitter, basado en las menciones a las cuentas oficiales de las Asambleístas ecuatorianas electas para el periodo 2021-2025.](#construccion-conjunto-datos)
  - [Arquitectura del modelo](#arquitectura-de-modelo)
  - [Arquitectura del prototipo](#arquitectura-del-prototipo)
  - [Entrenamiento del modelo](#entrenamienro-de-modelo)
  - [Evaluar el modelo](#Evaluar-modelo)
  - [Creación de la Api de Twitter](#Creación-api-twitter)
  - [Interfaz](#interfaz)
- [Guía de usuario](#guía-de-usuario)
- [Información adicional](#información-adicional)

## Autor
---
El presente Trabajo de Titulación fue desarrollado por:
-   Edmundo José Pezantes Urrego - Edmundo.j.pezantes@unl.edu.ec

## Introducción
---
El presente repositorio almacena los archivos utilizados para el desarrollo del trabajo de titulacion "Modelo de lenguaje utilizando RoBERTuito, para identificar tweets con contenido de violencia política de género hacia las asambleístas electas en Ecuador para el periodo 2021-2025", se encuentra divido en carpetas en las cuales se pueden encontrar los archivos que fueron necesarios para el desarrolo del presente TT.

## Desarrollo
---
El objetivo del presente trabajo es construir un modelo de lenguaje utilizando RoBERTuito, para identificar tweets con contenido de violencia política de género hacia las asambleístas electas en Ecuador para el periodo 2021-202.

- ## Construcción del conjunto de datos proveniente de la red social Twitter, basado en las menciones a las cuentas oficiales de las Asambleístas ecuatorianas electas para el periodo 2021-2025.
---
A través de la librería Snscrape de Python, se obtuvieron los tweets.

![image](https://github.com/Computacion-UNL/tw_violencia_genero/assets/50312849/2747fede-f2ce-48a0-8ad9-50605f6b0306)

Posteriormente se utilizó la libreria regex para el uso de expresiones regulares para realizar la limpieza y preprocesamiento de los datos.

![image](https://github.com/Computacion-UNL/tw_violencia_genero/assets/50312849/73e2fa4e-1c13-4178-b2c4-cb8b14b66e79)

Para el balanceo del conjunto de datos se empleó de la tecnica de Oversampling.

![image](https://github.com/Computacion-UNL/tw_violencia_genero/assets/50312849/d54a2604-2f21-4ae6-a7d7-8774d9f30e99)

Una vez balanceado el conjunto de datos, para dividirlo en conjunto de entrenamiento, validación y prueba, se empleó la biblioteca Hugging Face Datasets de Python.

![image](https://github.com/Computacion-UNL/tw_violencia_genero/assets/50312849/dee0347f-ed76-455b-9b51-c3dcc7c7d82c)

Se utilizó la biblioteca tokenizer para dividir el texto de los tweets en unidades discretas llamadas tokens, que son las representaciones básicas de las palabras en el modelo.

![image](https://github.com/Computacion-UNL/tw_violencia_genero/assets/50312849/de424509-0c8e-49ac-b566-4202a74c2952)

- ## Arquitectura del modelo
---
Esquema general del entrenamiento del modelo.

<div align="center">
	<img src ="https://github.com/Computacion-UNL/tw_violencia_genero/assets/50312849/53d4676b-c2cf-45f6-8084-e0fae16a544c" scale="350" height="300"/>
</div>

- ## Arquitectura del prototipo
---
La arquitectura fue destinada para implementarla en una aplicación web.

<div align="center">
	 <img src ="https://github.com/Computacion-UNL/tw_violencia_genero/assets/50312849/d255f5c9-8061-4984-bc18-7fb2b82a622c" scale="350" height="300" />
</div>
 
La arquitectura como se manifiesta en la Ilustración anterior, en la cual se observar el funcionamiento e interacciones entre los componentes empleados en el desarrollo del prototipo.

- ##Entrenamiento del modelo de lenguaje creado utilizando RoBERTuito.
---
Para entrenar el modelo, se empleó el lenguaje de programación Python con Pytorch que es una librería de aprendizaje automático, y la librería Transformers la cual proporciona arquitecturas de uso general, esto en conjunto con la herramienta Google Colab, puesto que permite hacer uso de sus GPU’s que son de buenas características.

![image](https://github.com/Computacion-UNL/tw_violencia_genero/assets/50312849/4988cef5-7b01-404a-a083-ce631eecbfdc)

- ## Evaluar el modelo entrenado.
---
Para evaluar el rendimiento del modelo se procedió a utilizar el conjunto de datos de prueba que es distinto al de entrenamiento.

![image](https://github.com/Computacion-UNL/tw_violencia_genero/assets/50312849/d87cea3c-d6ab-4228-aac1-f8a61567ea1f)

- ## Creación de la Api de Twitter.
---
Para poder extraer los tweets fue necesaria la creación de la API de twitter, para descargarlos en tiempo real con Tweepy, para lo cual lo primero que se debe realizar es crear una cuenta de desarrolladores en la plataforma de Twitter. Una vez creada la cuenta de desarrollador se tiene acceso a los tokens de acceso y los de consumo.

![image](https://github.com/Computacion-UNL/tw_violencia_genero/assets/50312849/296c04f8-4eb5-4287-80ee-9f41768d2e48)

Para hacer uso de los tokens y que los mismos no sean visibles se procedió a almacenarlos en un archivo .tomls para poder llamar a las variables que los almacenan desde el editor de código. Una vez almacenados los tokens se procedió a configurar y llamar a las variables que los almacenan.

![image](https://github.com/Computacion-UNL/tw_violencia_genero/assets/50312849/a8611176-17a2-4f47-a0c2-06c4af6bda03)

Para realizar peticiones a la API de Twitter se procedió a identificar con los tokens que se configuraron anteriormente. Tweepy tiene una función integrada llamada OAuthHandler para facilitarlo. 

![image](https://github.com/Computacion-UNL/tw_violencia_genero/assets/50312849/57742e78-5457-4c8c-9f5e-45a71d4f2148)

A continuación, se procedió a realizar la creación y llamada a la API para lo cual se configura la función API con la variable auth.

![image](https://github.com/Computacion-UNL/tw_violencia_genero/assets/50312849/1d4be651-2140-4bac-a2bd-2eb767b84c4d)
 
- ## Interfaz
---
Finalmente se codifico la parte de la interfaz, la cual se la codifico con la librería Streamlit, se agregaron los campos necesarios para su funcionamiento, los cuales le permiten al usuario realizar una búsqueda de su de ususuario de twitter o sus nombres y apellidos y el numero de tweets desea obtener. 

<div align="center">
	 <img src ="https://github.com/Computacion-UNL/tw_violencia_genero/assets/50312849/53055e0e-a6b5-4f1c-aef5-e7fbb4e94f83" width="600" height="350" />
</div>

El resultado final de este proyecto lo puede ver <A HREF="https://huggingface.co/spaces/JosePezantes/Violencia-politica-genero"> aqui. </A>



## Guía de usuario
---
El prototipo, se carácteriza por tener un menú, el cúal ofrece una sección de "Opciones", que se compone de:  <br/>

Selección del tipo de búsqueda: 
  - Término: Esta búsqueda se realiza para analizar lo que publican hacia su usuario de twitter o sus nombres y apellidos
  - Usuario: Esta búsqueda se realiza para analizar los tweets publicados por parte de un usuario de twitter en específico<br/>

Ingresar el numero de tweets a analizar:
  - De 1 a 50, por la restricción de la Api de twitter.
Página principal:
  - Cuadro de búsqueda: para poder introduccir los datos de búsqueda.
  - Cuadro de resultado: se presentan los resultados de los datos ingresados en una tabla conformada por los tweets con su respectiva clasificación.

## Información adicional
---

Las Tecnologías y Herramientas utilizadas fueron:
 - Plataforma de Google Colaboratory
 - Lenguaje de Programación Pyhton versión > 3.6
 - Framework Pytorch
 - Framework Streamlit
 - Tweepy==4.6.0
 - Pysentimiento
<br/>

