# goodmeal-test

## Instalación

Requisitos:
```
composer
docker
docker-compose
```

Estructura del proyecto:

- apps (apps folder)
    - backend (laravel app)
    - frontend (vuejs app)
- docker (config files)

Se puede correr ambos proyectos sin docker para esto..
Instalar dependencias en los proyectos:
```
composer install
npm install
```
Etc..

Si se continúa con docker:
Editar archivo hosts del equipo y agregar:

```
127.0.0.1 backend.local
127.0.0.1 frontend.local
```

Compilar e iniciar docker:
```
docker-compose build && docker-compose up -d 
```

Abrir en el navegador: http://frontend.local
Para la documentación del Api: http://backend.local/api/documentation

## Consideraciones y respuestas al test
- Backend construido en laravel 8.x
- Frontend con Vuejs 3 y Tailwind (Se optó por una app separada por la dockerización, aunque se podría incluir dentro de laravel)
- Para la documentación del api se usó L5-Swagger
- Solo se realizó test funcionales
- Faltó organización con docker, pero tiene lo básico y está funcional.

RESPUESTAS A LA PARTE 2
- Como se te ocurre un modelo para almacenar la distancia de tiendas?
- Como podemos hacer que el calculo de distancia de tiendas, sea rapido?
R. Respondo a las dos primeras preguntas: La distancia entre dos puntos o coordenadas se puede calcular con formulas y funciones matemáticas. Con esto podemos tener un aproximado y si a esto agregamos variables de tráfico por horas, tipo de vehículo u otros (considerando los tiempos de entrega historicos de una zona) se puede tener menos margen de error en cuando a distancias y tiempos de entrega. y con el mismo método podemos traer directamente en consultas sql las tiendas cercanas a una posición. (en el modelo Store he dejado un pequeño ejemplo)
- Como podemos disminuir el consumo del servicio de terceros ?
R. Con lo anterior mencionado. Sí,
- Como podemos optimizar la respuesta de nuestro servicio ?
R. Usando bases de datos no relacionales, sistemas de caché a consultas frecuentes y repetitivas y  quizá redes reuronales.

## About

Demo realizado por:
Richard Cuizara
