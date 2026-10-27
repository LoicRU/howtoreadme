> 💡 **Note pédagogique aux étudiants de 1ère année (Epitech / Tech)**
> 
> Ce repository et ce README servent d'**exemple de référence** pour vos projets. Il a été réalisé dans le cadre de mon **projet de fin d'année**.
>
> **Pourquoi ce README est un bon modèle ?**
> - **Clarté & Structure** : Un titre clair, des badges, des sections bien découpées et une navigation fluide.
> - **Exhaustivité des instructions** : Un étudiant ou correcteur doit pouvoir installer, lancer (via Docker ou en local) et tester le projet sans vous poser de questions.
> - **Transparence technique** : Arborescence explicite, technologies listées, et endpoints principaux indiqués.
> - **Professionnalisme** : Présentation visuelle soignée (emojis, blocs de code propre, structure standard de l'industrie).

---

# 💼 JobAggregator

[![Status](https://img.shields.io/badge/Status-Exemple%20P%C3%A9dagogique-blue.svg)]()
[![Stack](https://img.shields.io/badge/Stack-React%20%7C%20Node.js%20%7C%20FastAPI%20%7C%20Docker-brightgreen.svg)]()

---

## 🎯 Présentation du projet

**JobAggregator** est une plateforme web d'aide à la recherche d'emploi pour les profils tech.  
Son objectif est de **centraliser des offres**, les **rendre lisibles rapidement** et proposer des **outils IA utiles à la candidature**.

Le projet s'appuie sur trois briques principales :

- un **frontend React/Vite** pour la navigation et l'UX
- un **backend Node.js/Express + Prisma** pour l'API, l'authentification et la logique métier
- un **service IA Python/FastAPI** connecté à **Ollama** pour générer du contenu candidat

### Fonctionnalités principales :

- 🔐 Authentification et gestion de profil
- 🔍 Recherche et consultation d'offres
- ⭐ Favoris et suivi des candidatures
- 📊 Dashboard admin et recruteur
- 🤖 Assistant IA pour **CV**, **lettre de motivation** et **préparation d'entretien**

---

## 📁 Structure du projet

```text
.
├── README.md
├── docker-compose.yml
├── frontend/        # Interface React + Vite
├── backend/         # API Express + Prisma + PostgreSQL
├── back/            # Microservice IA FastAPI + Ollama
├── docs/            # Documentation produit, technique et projet
├── doc/             # Notes et documentation IA complémentaire
└── IA-design/       # Prototype de dashboard / POC historique
```

---

## 🚀 Installation et lancement

### 🔧 Prérequis

- **Docker** et **Docker Compose**
- **Ollama** installé localement (pour la partie IA)

---

### 📥 Installation

```bash
# Clonez le dépôt
git clone git@github.com:BipBIp-Epi/Site_BipBip.git Jobagreedeploy
cd Jobagreedeploy

# Copie des variables d'environnement
cp backend/.env.example backend/.env
```

---

### 🤖 Préparer le modèle IA

Le service `back/` appelle **Ollama en local**.  
Avant le lancement, il faut démarrer Ollama et télécharger le modèle :

```bash
ollama serve
ollama pull qwen2.5:0.5b
```

**Spécifications du modèle :**
- Modèle : `qwen2.5:0.5b`
- Taille : ~**398 MB**
- Usage : 100% local, sans API externe payante

---

### 🐳 Lancement rapide avec Docker

```bash
docker compose up --build
```

**Services disponibles :**
- 💻 **Frontend** : `http://localhost:5173`
- ⚙️ **Backend** : `http://localhost:8000`
- 🧠 **Service IA** : `http://localhost:8010`
- 🗄️ **PostgreSQL** : `localhost:5432`

---

### 🧪 Lancement en développement local (sans Docker pour l'app)

#### 1. Base de données
```bash
docker compose up -d db
```

#### 2. Backend API
```bash
cd backend
npm install
npx prisma generate
npx prisma migrate dev
npx prisma db seed
PORT=8000 npm run dev
```

#### 3. Service IA
```bash
cd back
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
OLLAMA_HOST=http://127.0.0.1:11434 OLLAMA_MODEL=qwen2.5:0.5b uvicorn app:app --host 0.0.0.0 --port 8010
```

#### 4. Frontend
```bash
cd frontend
npm install
VITE_API_URL=http://localhost:8000 npm run dev
```

---

## ⚡ Utilisation & Endpoints

Le projet expose notamment les routes principales suivantes :

- `/auth` : Inscription, connexion, profil
- `/api/offers` : Recherche et consultation d'offres
- `/api/applications` : Gestion des candidatures
- `/api/favorites` : Favoris
- `/api/ai` : Génération CV, lettre et questions d'entretien
- `/admin` : Routes d'administration

**Health checks utiles :**
```bash
curl http://localhost:8000/health
curl http://localhost:8010/health
```

---

## 🛠 Technologies utilisées

- **Frontend** : React 19, Vite, Tailwind CSS
- **Backend API** : Node.js, Express, Prisma ORM
- **Base de données** : PostgreSQL
- **Microservice IA** : Python, FastAPI, Ollama
- **Tests** : Vitest, Testing Library
- **DevOps / Infra** : Docker, Docker Compose

---

## 📊 Résultats clés

- Agrégation et normalisation d'offres tech en temps réel.
- Parcours utilisateurs différenciés (Candidats, Recruteurs, Admins).
- Génération assistée de documents de candidature via IA locale.
- Architecture microservices découplée, testable et démontrable.

---

## ✅ Tests

```bash
# Lancer les tests du backend
cd backend && npm test

# Lancer les tests du frontend
cd frontend && npm test
```

---

## 👥 Contributeurs & Cadre

Ce projet a été développé dans le cadre d'un **projet de fin d'année** et sert aujourd'hui de **support pédagogique d'exemple** pour les étudiants.

Pour consulter l'historique complet des contributions, merci de vous référer aux commits du dépôt Git.