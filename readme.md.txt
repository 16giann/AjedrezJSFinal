#AJEDREZ 

Entrega N3 - Desarrollo Web y Móvil  
Autor: Gianfranco Caleni

Juego de ajedrez en línea desarrollado con Node.js y Express.  
Permite crear partidas, invitar a otros jugadores, jugar en tiempo real  
y gestionar movimientos sobre un tablero interactivo.

---

#Tecnologías

- **Node.js** + **Express.js**
- **MongoDB** (con Mongoose)
- **express-session** (gestión de sesiones)
- **Handlebars** (vistas)
- **PM2** (ejecución persistente en producción)
- HTML, CSS (sin frameworks frontend)

#Instalación

1.Clona el repositorio:

    ```bash
    git clone https://github.com/tuusuario/ajedrez.git
    cd ajedrez
    ```

2.Instala dependencias:

    ```bash
    npm install
    ```

3.Configura tu archivo `.env`:

    ```
    MONGO_URI=mongodb://localhost:27017/ajedrez
    PORT=3000
    ```

4.Para desarrollo puedes correr:

    ```bash
    node server.js
    ```

---

#Producción con PM2

Para producción se recomienda correr el servidor con PM2:

- Iniciar el servidor:

    ```bash
    pm2 start server.js --name ajedrez
    ```

- Reiniciar:

    ```bash
    pm2 restart ajedrez
    ```

- Detener:

    ```bash
    pm2 stop ajedrez
    ```

- Eliminar proceso:

    ```bash
    pm2 delete ajedrez
    ```

---

#Scripts en package.json

```json
"scripts": {
  "start": "pm2 start server.js --name ajedrez",
  "pm2-restart": "pm2 restart ajedrez",
  "pm2-stop": "pm2 stop ajedrez",
  "pm2-delete": "pm2 delete ajedrez"
}

#ESTRUCTURA DE LA PAGINA

AJEDREZ/
│
├── .env                     # Variables de entorno (MONGO_URI, etc.)
├── package.json             # Configuración de npm y scripts
├── package-lock.json
├── ecosystem.config.js      # Configuración avanzada de PM2 (opcional)
├── readme.md
├── server.js                # Servidor Express principal
│
├── models/                  # Modelos de datos Mongoose
│   ├── usuario.js
│   └── partida.js
│
├── public/                  # Archivos públicos estáticos
│   ├── estilos.css
│   ├── script.js
│   └── uploads/             # Avatares u otros archivos subidos
│
├── views/                   # Plantillas Handlebars
│   ├── layouts/
│   │   └── main.hbs         # Layout base
│   ├── home.hbs
│   ├── login.hbs
│   ├── registro.hbs
│   ├── play.hbs
│   ├── eliminar-partida.hbs
│   ├── perfil.hbs
│   ├── historia.hbs
│   └── desarrollador.hbs
│
└── .vscode/                 # Configuración del entorno de desarrollo (opcional)
