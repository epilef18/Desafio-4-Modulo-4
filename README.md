# Sistema de Encuestas  

## Descripción  
Este proyecto consiste en el desarrollo de un sistema de encuestas para una consultora. El software permite crear y contestar encuestas, estableciendo relaciones entre usuarios, preguntas, alternativas y respuestas.

## Requisitos  
El sistema maneja las siguientes entidades principales:  

### Alternativas  
- Una alternativa tiene:
  - Contenido (texto).
  - Ayuda (texto, opcional).  
- Reglas:
  - Solo puede existir como parte de una pregunta.  
  - Puede ser consultada y modificada libremente.  
- Mecanismo:
  - Mostrar el contenido y la ayuda (si existe).  

### Preguntas  
- Una pregunta tiene:
  - Enunciado (texto).
  - Ayuda (texto, opcional).
  - Indicador de si es requerida (booleano).
  - Lista de alternativas.  
- Reglas:
  - Solo puede existir como parte de una encuesta.  
  - El enunciado, la ayuda y el estado requerido pueden consultarse y modificarse libremente.
  - Las alternativas solo pueden ser consultadas.  
- Mecanismo:
  - Mostrar el enunciado, la ayuda (si existe) y las alternativas (con su ayuda, si existe).  

### Encuestas  
- Una encuesta tiene:
  - Nombre (texto).
  - Lista de preguntas.
  - Lista de listados de respuestas (vacía al inicio).  
- Reglas:
  - Solo el nombre puede consultarse y modificarse libremente.  
- Mecanismos:
  - Mostrar el nombre, preguntas (con su ayuda) y alternativas (con su ayuda).  
  - Agregar un listado de respuestas.  

#### Tipos específicos de encuestas:  
1. **Encuestas limitadas por edad**:  
   - Tienen una edad mínima y máxima (números enteros).  
   - Reglas especiales para modificar las edades.  
   - Al agregar un listado de respuestas, se valida que la edad del usuario esté en el rango permitido.  

2. **Encuestas limitadas por región**:  
   - Contienen una lista de regiones (números enteros).  
   - Reglas especiales para modificar las regiones.  
   - Al agregar un listado de respuestas, se valida que la región del usuario esté en la lista permitida.  

### Listado de Respuestas  
- Está asociado a un usuario que lo generó.  
- Contiene:
  - Una lista de respuestas (números enteros).  
- Reglas:
  - El usuario y las respuestas solo pueden ser leídas, no modificadas libremente.  
  - Solo puede existir como parte de una encuesta.  

### Usuarios  
- Un usuario tiene:
  - Correo (texto).  
  - Edad (número entero).  
  - Región (número entero).  
- Reglas:
  - Los datos pueden ser leídos y modificados mediante mecanismos específicos.  

## Funcionalidades  
1. Crear encuestas y preguntas.  
2. Agregar alternativas a las preguntas.  
3. Responder encuestas mediante un mecanismo que:  
   - Valida restricciones de edad y región (si aplica).  
   - Almacena las respuestas de un usuario.  

## Instalación  
1. Clona este repositorio:  
   ```bash
   git clone https://github.com/tu_usuario/sistema-encuestas.git
   cd sistema-encuestas
