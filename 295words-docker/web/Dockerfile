# BUILD
# use the build platforms matching arch rather than target arch
FROM --platform=linux/amd64 golang:alpine as builder

WORKDIR /app

COPY . .
# build for the target arch not the build platform host arch
RUN go build -o main dispatcher.go

# Crea una nueva etapa para el contenedor final (multi-stage build)
FROM alpine:latest

# Establecer el directorio de trabajo dentro del contenedor final
WORKDIR /app

# Copiar el binario desde la etapa de compilación
COPY --from=builder /app/main .

# Copiar la carpeta estática al contenedor final
COPY static ./static

# Exponer el puerto que utiliza la aplicación
EXPOSE 80

# Comando para ejecutar el binario
CMD ["./main"]