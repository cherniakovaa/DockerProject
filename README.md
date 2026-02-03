# Azure Voting App (Docker + Redis)

## Opis projektu

Projekt przedstawia prostą aplikację do głosowania (koty vs psy), uruchamianą w środowisku kontenerowym przy użyciu **Docker Compose**.  
Aplikacja składa się z dwóch kontenerów:

- **Frontend** – aplikacja webowa (Python / Flask), umożliwiająca oddawanie głosów
- **Backend** – baza danych **Redis**, w której zapisywane są głosy

Projekt bazuje na oficjalnym przykładzie Microsoft Azure Voting App i został dostosowany do pracy lokalnej z użyciem Dockera.

Repozytorium bazowe:
https://github.com/Azure-Samples/azure-voting-app-redis

---

## Technologie

- Docker
- Docker Compose
- Redis
- Python (Flask)
- Git / GitHub

---

## Architektura aplikacji

Aplikacja składa się z dwóch serwisów uruchamianych w `docker-compose.yaml`:

1. **azure-vote-front**
   - interfejs webowy dostępny w przeglądarce
   - komunikuje się z Redisem po nazwie serwisu

2. **azure-vote-back**
   - kontener z Redisem
   - przechowuje liczbę głosów na koty i psy w pamięci

Komunikacja pomiędzy kontenerami odbywa się wewnątrz sieci Dockera.

---

## Zmienne środowiskowe (.env)

Projekt wykorzystuje plik `.env`, który **nie jest dodawany do repozytorium**.

### Przykład

```env
REDIS_PORT=6379
FRONT_PORT=8080
