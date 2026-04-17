# williamsManriqueRojas

# Arquitectura Distribuida en AWS con Docker

## Descripción
Proyecto que implementa una arquitectura distribuida con:

- Frontend: Angular
- Backend: Spring Boot
- Base de datos: SQL Server en Docker
- Infraestructura: AWS EC2

---

## Arquitectura

Frontend → Backend → Database

- Angular consume API REST
- Spring Boot conecta con SQL Server
- Comunicación mediante IP privada en AWS

---

## nfraestructura AWS

- EC2 Frontend (Angular + Nginx)
- EC2 Backend (Spring Boot API)
- EC2 Database (SQL Server Docker)

---

## Docker

Cada componente está dockerizado:

- Dockerfile en frontend
- Dockerfile en backend
- SQL Server en contenedor oficial

---

## Endpoints

GET /datos → retorna lista de productos

---

## Configuración Backend

spring.datasource.url=jdbc:sqlserver://IP_DB:1433;databaseName=proyecto_db
spring.datasource.username=sa
spring.datasource.password=TuPassword123!

---

## Ejecución

### Backend
docker build -t backend-app .
docker run -p 8080:8080 backend-app

### Frontend
docker build -t frontend-app .
docker run -p 80:80 frontend-app

### Database
docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=TuPassword123!' -p 1433:1433 mcr.microsoft.com/mssql/server

---

