## Télécharger le projet complet
Le projet complet avec des données volumineuses est disponible ici : 
https://drive.google.com/drive/folders/1YcKIlMBv5kpVM9dFKDSq-c8jIl7i2SC3?usp=sharing

**Révolutionnez l'expérience client avec notre solution hôtelière IA**

Système de gestion complet avec assistant vocal intelligent permettant aux clients de réserver par la voix dans leur langue natale, tandis que les hôteliers bénéficient d'un dashboard moderne pour gérer stocks, réservations et statistiques.
# HotelAI - Backend & AI

Backend robuste et système d'IA intelligent pour la gestion hôtelière automatisée, développé avec FastAPI et intégrant des capacités de traitement vocal multilingue.

##  Fonctionnalités

###  Core Backend
- **API RESTful** avec FastAPI et documentation Swagger automatique
- **Authentification JWT** avec gestion des rôles (admin/hotel)
- **Base de données asynchrone** avec SQLAlchemy et PostgreSQL
- **Gestion complète des réservations** avec historique des actions
- **Système de stock de chambres** (simple, double, triple)
- **Gestion des disponibilités** en temps réel
- **API administrateur** pour la gestion multi-hôtels

###  Intelligence Artificielle
- **Assistant vocal intelligent** avec reconnaissance multilingue
- **Traitement du langage naturel** (français, arabe, darija)
- **Extraction automatique d'entités** (dates, noms, type de chambre)
- **Synthèse vocale** avec détection automatique de langue
- **Vérification automatique des disponibilités**

##  Stack Technique

### Backend
- **FastAPI** - Framework API moderne et rapide
- **SQLAlchemy** - ORM asynchrone
- **PostgreSQL** - Base de données relationnelle
- **JWT** - Authentification sécurisée
- **Pydantic** - Validation des données
- **Python 3.8+** - Langage de programmation

### AI & Audio
- **OpenAI GPT-4o** - Compréhension du langage naturel
- **OpenAI Whisper** - Reconnaissance vocale
- **gTTS** - Synthèse vocale multilingue
- **LangDetect** - Détection automatique de langue

##  Modèles de Données

  ### User
  - Gestion des comptes administrateur et hôtel
  - Authentification JWT
  - Rôles et permissions
  
  ### HotelRoomStock
  - Stock initial par type de chambre
  - Relation one-to-one avec User
  
  ### Reservation
  - Informations complètes de réservation
  - Dates, type de chambre, nombre de personnes
  - Statut et historique
  
  ### DailyRoomAvailability
  - Disponibilités journalières calculées
  - Synchronisation automatique avec les réservations
  ## Système d'IA
  
  ### Capacités Multilingues
  - **Français** - Support complet
  - **Arabe classique** - Compréhension et réponse
  - **Darija marocain** - Support dialectal avancé
  
  ### Processus de Réservation Vocale
  1. **Transcription audio** → Texte avec Whisper
  2. **Détection de langue** → Adaptation automatique
  3. **Extraction d'entités** → GPT-4o analyse la requête
  4. **Gestion de contexte** → Maintien de la conversation
  5. **Vérification disponibilité** → Appel API backend
  6. **Création réservation** → Validation et confirmation
  7. **Réponse vocale** → Synthèse dans la langue détectée
### Entités Extraites
- `guest_name` - Nom du client
- `type_de_chambre` - Mapping automatique (simple/double/triple)
- `nombre_de_personnes` - Conversion texte→nombre
- `date_arrivee` & `date_depart` - Normalisation des dates

##  Installation et Configuration

  ### Prérequis
  - Python 3.8+
  - PostgreSQL
  - Clé API OpenAI

### Installation
  # Cloner le repository
  git clone https://github.com/hajarelkamri/Ai-Agent
  cd hotelai-backend
  
  # Créer environnement virtuel
  python -m venv venv
  source venv/bin/activate  # Linux/Mac
  # ou
  venv\Scripts\activate     # Windows
  
  # Installer les dépendances
  pip install -r requirements.txt
  
  # Démarrage
  uvicorn app.main:app --reload --host 0.0.0.0 --port 8080

# Workflow de Réservation IA
  Réception audio → Fichier WAV temporaire
  
  Transcription → Texte avec Whisper
  
  Analyse GPT → Extraction structured des entités
  
  Vérification contexte → Questions complémentaires si besoin
  
  Appel disponibilité → Vérification backend
  
  Création réservation → Appel API avec token hôtel
  
  Nettoyage → Suppression fichiers temporaires
  
  Réponse audio → Synthèse dans la langue appropriée
  
# Fonctionnalités Avancées
  # Gestion de Session
    Contexte maintenu par session ID
    
    Détection et mémorisation de la langue
    
    Gestion des conversations multi-tours
    
    Mapping Intelligent
    Reconnaissance des types de chambre dans toutes les langues
    
    Conversion des dates (formats variés → ISO)
    
    Interprétation des nombres (texte → chiffres)
  # Gestion d'Erreurs
    Fallback multilingue pour les erreurs
    
    Reconnaissance des requêtes incomplètes
    
    Messages d'erreur contextuels


# HotelAI - Frontend

Interface d'administration moderne pour la gestion hôtelière, développée avec React et Tailwind CSS.

##  Fonctionnalités

  ###  Authentification
  - Page de connexion sécurisée avec validation JWT
  - Redirection automatique selon le rôle (admin/hôtel)
  - Gestion des tokens et déconnexion
  
  ###  Espace Administrateur
  - **Gestion des hôtels** : Création, modification, suppression d'hôtels
  - **Activation/Désactivation** : Contrôle du statut des établissements
  - **Tableau de bord** : Vue d'ensemble complète
  
  ###  Espace Hôtelier
  - **Tableau de bord** : Statistiques en temps réel (occupation, réservations)
  - **Gestion des chambres** : Stock et disponibilités par type
  - **Réservations** : Consultation des réservations en cours
  - **Historique** : Journal des actions et modifications
  
  ##  Technologies Utilisées
  
  - **React 18** - Framework frontend
  - **React Router DOM** - Navigation SPA
  - **Tailwind CSS** - Styling et design responsive
  - **Axios** - Requêtes HTTP
  - **HTML5/CSS3** - Structure et style
  
## Interface Utilisateur
  Pages Principales: 
  # Login (/login)
  
  Design moderne avec fond d'écran
  
  Formulaire de connexion centré
  
  Gestion des erreurs
  
  # Admin (/admin)
  
  Tableau de gestion des hôtels
  
  Formulaire d'ajout inline
  
  Actions rapides (activer/supprimer)
  
  # Dashboard Hôtel (/hotel/dashboard)
  
  Widgets statistiques (chambres, réservations, occupation)
  
  Prochains check-in/check-out
  
  Design responsive
  
  # Gestion Chambres (/hotel/rooms)
  
  Édition du stock (simple, double, triple)
  
  Calendrier des disponibilités
  
  Tableaux interactifs
  
  # Réservations (/hotel/reservations)
  
  Liste des réservations en cours
  
  Informations détaillées clients
  
  Design tableau clair
  
  # Historique (/hotel/history)
  
  Journal des actions
  
  Timestamps et détails
  
  Interface de consultation

## Sécurité
  Validation JWT sur chaque requête
  
  Redirection automatique si non authentifié
  
  Gestion des rôles (admin/hotel)
  
  Stockage sécurisé des tokens
