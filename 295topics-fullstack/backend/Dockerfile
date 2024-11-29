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

# Compila el código TypeScript a JavaScript
RUN npm run build

# Expone el puerto en el que corre el backend
EXPOSE 5000

# Comando para iniciar la aplicación
CMD ["npm", "run", "start"]
