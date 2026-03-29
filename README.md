# 🐧 Penguin On The Way!

Proyecto de arquitectura cloud en AWS orientado a demostrar competencias en **Cloud Architecture y DevOps**, mediante el despliegue completo de una aplicación web en una infraestructura escalable, resiliente y segura.

---

## 📌 Descripción

**Penguin On The Way!** es una aplicación web que permite registrar tickets a través de un formulario.  

Cada solicitud:

- Se almacena en una base de datos **RDS MySQL**
- Genera una notificación mediante **SNS**
- Es procesada por un backend en **Flask**

La aplicación está desplegada sobre una arquitectura en AWS basada en múltiples capas y diseñada siguiendo buenas prácticas.

---

## 🏗️ Arquitectura

La solución está estructurada en las siguientes capas:

### 🔹 Capa de red
- VPC con subnets públicas y privadas  
- NAT Gateway  
- Network ACLs  
- VPC Flow Logs  

### 🔹 Capa de seguridad
- Security Groups por componente (ALB, EC2, RDS)  
- VPC Endpoint para SNS (tráfico privado)  

### 🔹 Capa de datos
- RDS MySQL en **Multi-AZ**  
- Backups automáticos y snapshots  

### 🔹 Capa de aplicación
- Application Load Balancer (ALB)  
- Auto Scaling Group  
- EC2 con **NGINX + Gunicorn + Flask**  

### 🔹 Observabilidad
- CloudWatch Logs y métricas  
- Alarmas con SNS  
- CloudTrail  
- VPC Flow Logs  

---

## ⚙️ Tecnologías utilizadas

### ☁️ AWS
- EC2, ALB, Auto Scaling  
- RDS (MySQL)  
- SNS  
- CloudWatch  
- CloudTrail  
- VPC, NAT Gateway, VPC Endpoint  

### 🧱 Infraestructura como Código
- AWS CloudFormation  

### 🐍 Backend
- Python (Flask)  
- Gunicorn  

### 🎨 Frontend
- HTML, CSS, JavaScript  

### 🌐 Servidor web
- NGINX  

---

## 🚀 Flujo de despliegue

El despliegue se realiza de forma modular mediante CloudFormation:

1. Capa de red  
2. Security Groups  
3. VPC Endpoint  
4. Capa de datos (RDS)  
5. SNS  
6. Capa de aplicación (ALB + ASG + EC2)  

---

## 🖥️ Arquitectura de la aplicación

Cliente → ALB → NGINX → Gunicorn → Flask → RDS
↓
SNS

- **NGINX** actúa como reverse proxy  
- **Gunicorn** ejecuta la aplicación Flask  
- **Flask** gestiona la lógica de negocio  
- **RDS** almacena los datos  
- **SNS** envía notificaciones  

---

## 📂 Estructura del proyecto

├── network-stack.yaml
├── security-groups.yaml
├── vpc-endpoint.yaml
├── data-stack.yaml
├── sns.yaml
├── app-stack.yaml
├── script-bash-ami-potw
├── script-bash-ami-potw-explicado
├── diagrama-POTW.io
└── README.md


---

## 📊 Funcionalidades demostradas

- Infraestructura desplegada con IaC (CloudFormation)  
- Arquitectura en múltiples capas  
- Alta disponibilidad (Multi-AZ)  
- Escalabilidad automática (Auto Scaling)  
- Monitorización y alertas  
- Centralización de logs  
- Auditoría de accesos  
- Backups y recuperación  

---

## 🧠 Competencias demostradas

- Diseño de arquitecturas en AWS  
- Infraestructura como Código  
- Networking avanzado (VPC, subnets, routing)  
- Seguridad en cloud  
- Administración Linux + Bash  
- Despliegue de aplicaciones web  
- Observabilidad y monitorización  
- Alta disponibilidad y resiliencia  
- Optimización de costes  

---

## 🔮 Mejoras futuras

- CI/CD (GitHub Actions / CodePipeline)  
- Docker + ECS/EKS  
- HTTPS con ACM + WAF  
- AWS Secrets Manager  
- Monitorización avanzada (tracing)  
- Arquitectura serverless  

---

## 📸 Demo

Incluye:
- Capturas de la arquitectura en AWS  
- Funcionamiento de la aplicación  
- Auto Scaling en acción  
- Alarmas y notificaciones  

---

## 📎 Script de despliegue de la aplicación

La AMI utilizada en el Auto Scaling Group se genera a partir de un script que instala:

- Python + Flask  
- Gunicorn  
- NGINX  
- Aplicación completa  

---

## 👨‍💻 Autor

Proyecto desarrollado por Carlos Fernández como práctica de **Cloud Architecture & DevOps**, enfocado a demostrar habilidades reales en entornos AWS.

