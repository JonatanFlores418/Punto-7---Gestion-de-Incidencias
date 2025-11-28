# 🚨 IMPORTANTE — LEER ANTES DE EJECUTAR 🚨

 ⚠️ Si levantás este proyecto con Docker desde este repositorio, el GLPI se iniciará completamente desde cero.
 Esto es intencional: la base de datos real del equipo no se puede subir a GitHub debido a limitaciones técnicas con los volúmenes de MySQL.

 ✔ Si querés ver el GLPI REAL con todas las incidencias, usuarios, categorías y trabajo del grupo, accedé aquí:
## 🔗 https://bicolor-nondescribable-karri.ngrok-free.dev

 Ese enlace expone el entorno original donde trabajó el equipo y donde se puede verificar el desarrollo completo del Punto 7.
## ¡¡¡ Tener en cuenta que si el ordenador donde se hostea el puerto NO ESTA ENCENDIDO, EL ENLACE NO FUNCIONARA!!!


## 📌 Documentacion de Gestión de Incidencias (GLPI)**

Este repositorio contiene la implementación del **Punto 7** del Trabajo Práctico Final, correspondiente a la **instalación, configuración y uso del sistema de gestión de incidencias GLPI**.

GLPI se despliega mediante **Docker + Docker Compose**, incluyendo:

* 📦 Contenedor con **GLPI (Web UI)**
* 🗄️ Contenedor con **MySQL** como base de datos
* 🔧 Configuración limpia para desplegar desde cero

---

# 🚀 **Cómo ejecutar este proyecto**

> **Requisitos previos:**
>
> * Tener **Docker Desktop** instalado
> * Tener **Docker Compose** habilitado

---

## ▶️ **1. Clonar el repositorio**

```sh
git clone https://github.com/TU_USER/TU_REPO.git
cd TU_REPO
```

---

## ▶️ **2. Levantar los contenedores**

```sh
docker compose up -d
```

Esto va a iniciar:

* `glpi-web` → servidor web de GLPI
* `glpi-db` → servidor MySQL configurado desde cero

---

## ▶️ **3. Acceder a GLPI**

Una vez levantado, abrir en el navegador:

```
http://localhost:8085
```

GLPI iniciará su instalador. Completar con los siguientes valores:

### **Datos de conexión a MySQL**

| Campo             | Valor      |
| ----------------- | ---------- |
| **Servidor SQL**  | `glpi-db`  |
| **Usuario SQL**   | `glpi`     |
| **Password SQL**  | `glpipass` |
| **Base de datos** | `glpidb`   |

Finalizado ese paso, GLPI quedará listo para usar.

---

# 🗂️ **Estructura del proyecto**

```
punto7-glpi/
│── glpi/          → Archivos de configuración y files de GLPI
│── mysql/         → Datos persistentes de MySQL
│── docker-compose.yml
│── README.md
```

---

# ⚠️ **Sobre la base de datos del proyecto**

Por razones técnicas, **no se pudo incluir en este repositorio la base de datos completa utilizada por el equipo**, ya que:

* Docker genera archivos binarios que **no pueden subirse correctamente a GitHub**.
* Los volúmenes de MySQL contienen datos internos propios del motor.
* Subirlos ocasiona errores de integridad y corrupción de la BD.

👉 **Por eso este Docker Compose inicia una base limpia desde cero**, solo con la estructura necesaria para usar GLPI.

---

# 🌐 **Acceso al GLPI real utilizado por el equipo**

Como alternativa, se habilitó un acceso remoto mediante **Ngrok**, que expone el GLPI real utilizado para trabajar en equipo durante todo el proyecto:

👉 **Acceso remoto al GLPI del grupo:**
🔗 [https://bicolor-nondescribable-karri.ngrok-free.dev](https://bicolor-nondescribable-karri.ngrok-free.dev)

Este enlace permite verificar:

* Las incidencias cargadas por el equipo
* Usuarios, perfiles y categorías
* Tareas, seguimiento y flujo real del proceso de gestión de incidencias

*(El enlace puede estar activo solo durante horarios de presentación, dado que depende del túnel local.)*

---

# 🧑‍🏫 **Nota para el profesor**

Este repositorio cumple con los requisitos del Punto 7:

* Instalación de GLPI con contenedores Docker
* Base de datos persistente MySQL
* Acceso web local y remoto
* Ejemplo reproducible desde cero
* Demostración del uso real mediante ambiente externo publicado por Ngrok

Para garantizar la correcta evaluación, se proporcionó un enlace directo al entorno donde el equipo trabajó las incidencias reales del proyecto.

---

# 🛠️ **Comandos útiles**

### Ver logs

```sh
docker logs glpi-web
docker logs glpi-db
```

### Reiniciar contenedores

```sh
docker compose restart
```

### Apagar todo

```sh
docker compose down
```

### Apagar + borrar volúmenes

```sh
docker compose down -v
```

---

