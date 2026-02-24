# TP DevSecOps avec Docker 🛡️

![Build and Scan](https://github.com/IsmaGSW78/DevOps_tp_docker_Charni/actions/workflows/docker-deploy.yml/badge.svg)
![CodeQL](https://github.com/IsmaGSW78/DevOps_tp_docker_Charni/actions/workflows/codeql.yml/badge.svg)

## Pipeline DevSecOps

Ce projet implémente un pipeline CI/CD sécurisé pour Docker avec :

- Analyse statique du code (CodeQL)
- Lint du Dockerfile (Hadolint)
- Scan de l'image Docker (Trivy)
- Scan des dépendances (Dependabot)
- SBOM (Software Bill of Materials)

## Architecture de Sécurité
Code → SAST → Hadolint → Build → Trivy → Security Gates → GHCR

## Sécurité de l'Image

- Image de base : nginx:alpine (version spécifique)
- Utilisateur non-root
- Headers de sécurité renforcés
- Health checks
- Pas de secrets dans l'image

## Exécution Locale

```bash
docker pull ghcr.io/[username]/devops-tp-docker-[nom]:main
docker run -p 8080:8080 ghcr.io/[username]/devops-tp-docker-[nom]:main
