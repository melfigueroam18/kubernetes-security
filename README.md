# kubernetes-security

Este repositorio contiene los **manifiestos de Kubernetes** necesarios para desplegar
una aplicación de **tres capas** (Frontend, API y Base de Datos) de forma **segura**.

---

## Arquitectura

- **Namespace dedicado**: `secure-app`
- **Frontend**
  - Deployment + Service (NodePort)
  - NGINX no-root
- **API**
  - Deployment + Service (ClusterIP)
  - Node.js no-root
- **Database**
  - StatefulSet + Service
  - PostgreSQL con volumen persistente

---

## Imágenes Docker utilizadas

- Frontend  
  `docker.io/melaniefig/frontend-security:1.0.0`

- API  
  `docker.io/melaniefig/api-security:1.0.0`

- Database  
  `docker.io/melaniefig/db-security:1.0.0`

---

## Estructura del repositorio

```text
.
├── k8s/
│   ├── namespace.yaml
│   ├── configmap.yaml
│   ├── secret.yaml
│   ├── db.yaml
│   ├── api.yaml
│   └── front.yaml
└── README.md

