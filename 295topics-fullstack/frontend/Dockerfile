# Usa la imagen oficial de Node.js
FROM node:18

# Establece el directorio de trabajo dentro del contenedor
WORKDIR /app

# Copia los archivos necesarios para instalar dependencias
COPY package*.json ./

# Instala dependencias
RUN npm install

# Copia el resto del código fuente
COPY . .

# Expone el puerto donde se sirve el frontend
EXPOSE 3000

# Comando para iniciar el servidor de la aplicación (si aplica)
CMD ["npm", "run", "start"]
