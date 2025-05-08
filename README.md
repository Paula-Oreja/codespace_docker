# Introducción a Docker

Docker es una plataforma de código abierto diseñada para automatizar el despliegue de aplicaciones dentro de contenedores de software. Estos contenedores proporcionan un entorno ligero, portátil y autosuficiente que garantiza que el software se ejecute de manera uniforme en diferentes sistemas.

## ¿Qué es un contenedor?

Un **contenedor** es una unidad estándar de software que empaqueta código y todas sus dependencias para que una aplicación se ejecute de forma rápida y confiable en distintos entornos. A diferencia de las máquinas virtuales, los contenedores no requieren un sistema operativo completo, lo que los hace más eficientes en términos de recursos.

## ¿Por qué usar Docker?

Algunas de las principales ventajas de Docker incluyen:

- **Portabilidad:** los contenedores funcionan de la misma manera en desarrollo, pruebas y producción.
- **Eficiencia:** uso mínimo de recursos comparado con máquinas virtuales.
- **Rapidez:** inicio casi instantáneo de contenedores.
- **Escalabilidad:** ideal para arquitecturas de microservicios y despliegues en la nube.

## Componentes clave de Docker

- **Docker Engine:** el motor que permite crear y ejecutar contenedores Docker.
- **Dockerfile:** archivo de texto que contiene instrucciones para construir una imagen Docker.
- **Imagen Docker:** plantilla inmutable utilizada para crear contenedores.
- **Contenedor Docker:** instancia en ejecución de una imagen.
- **Docker Hub:** repositorio público de imágenes Docker.

## Flujo de trabajo básico

1. Crear un `Dockerfile` con las instrucciones para construir la imagen.
2. Construir la imagen con `docker build`.
3. Ejecutar un contenedor a partir de la imagen con `docker run`.
4. (Opcional) Subir la imagen a Docker Hub con `docker push`.

## Ejemplo simple de Dockerfile

```Dockerfile
# Usar una imagen base
FROM python:3.10-slim

# Establecer el directorio de trabajo
WORKDIR /app

# Copiar archivos al contenedor
COPY . /app

# Instalar dependencias
RUN pip install --no-cache-dir -r requirements.txt

# Comando por defecto
CMD ["python", "app.py"]