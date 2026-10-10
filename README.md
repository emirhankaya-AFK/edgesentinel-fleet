# EdgeSentinel: Edge AI Vision Fleet Management

## English

### Purpose
EdgeSentinel is a comprehensive portfolio product for managing fleets of edge AI vision devices. It provides device registration, heartbeat monitoring, camera stream simulation, model registry with immutable versions and rollout states, inference event ingestion, alert acknowledgement, human review/feedback loop, drift metrics computation, offline edge queue with retry/sync behavior, audit logging, and a role-ready architecture.

### Features
- Device Management: Register and monitor edge devices via heartbeats  
- Model Registry: Store and manage AI model versions with immutability flags and rollout states  
- Event Ingestion: Receive and process inference events from edge devices  
- Alerting: Generate alerts based on drift, low confidence, or anomalies  
- Human Review: Workflow for human feedback on inferences  
- Drift Detection: Compute drift metrics from event confidence and feature statistics  
- Offline Support: Edge agent queues events during offline periods and syncs when back online  
- Audit Log: Comprehensive audit trail for all system actions  
- Role-Ready Architecture: Designed to support role-based access control (RBAC)

### Stack
- Backend: FastAPI, SQLAlchemy, Pydantic  
- Frontend: React, TypeScript, Vite  
- Edge Agent Simulator: Python  

### Setup & Usage
**Prerequisites**  
- Docker and Docker Compose  
- (Optional) Kubernetes cluster for production deployment  

**Running with Docker Compose**  
1. Clone the repository  
2. Navigate to the project directory  
3. Copy the example environment file: `cp backend/.env.example backend/.env`  
4. Edit the `.env` file if needed (for PostgreSQL connection)  
5. Start the services: `make up`  
6. Access the dashboard at http://localhost:3000  
7. The backend API will be available at http://localhost:8000  

**Running with Kubernetes**  
1. Apply the database storage class and PVC (if not already available)  
2. Apply the Kubernetes manifests: `kubectl apply -f kubernetes/`  
3. Access the frontend via the LoadBalancer service or set up an Ingress  

**Sample Data**  
To populate the database with sample data, run the sample data script:  
- Docker Compose: `docker-compose run --rm backend python kubernetes/scripts/sample_data.py`  
- Kubernetes: `kubectl run --rm -i --tty sample-data --image=edgesentinel-backend:latest --restart=Never -- python kubernetes/scripts/sample_data.py`  

### Testing
- Backend: Run `make test` to execute backend tests  
- Frontend: `make frontend` starts the frontend in development mode  
- Edge Agent Simulator: No specific test command documented  

### Limitations
No explicit limitations are documented in the README.

### License
This project is proprietary and confidential. All rights reserved.

## Türkçe

### Amaç
EdgeSentinel, edge AI görüntü cihazlarının filosunu yönetmek için kapsamlı bir portföy ürünüdür. Cihaz kaydı, heartbeat izleme, kamera akışı simülasyonu, değiştirilemeyen sürümler ve dağıtım durumlarıyla model kaydı, çıkarım eventi alımı, uyarı onayı, insan geri bildirim/denetim döngüsü, sapma metrikleri hesaplama, çevrimdışı kenar kuyruğu ile yeniden deneme/senkronizasyon davranışı, denetim günlüğü ve rol hazır mimarisi sağlar.

### Özellikler
- Cihaz Yönetimi: Kalp atışları üzerinden edge cihazlarını kaydedin ve izleyin  
- Model Kayıt Defteri: AI model sürümlerini değiştirilemez bayraklar ve dağıtım durumlarıyla saklayın ve yönetin  
- Olay Alımı: Edge cihazlarından çıkarım olaylarını alın ve işleyin  
- Uyarı: Sapma, düşük güven veya anomaliye dayalı uyarılar oluşturun  
- İnsan Denetimi: Çıkarım üzerinden insan geri bildirimi için iş akışı  
- Sapma Tespiti: Olay güven ve özellik istatistiklerinden sapma metriklerini hesaplayın  
- Çevrimdışı Destek: Edge ajanı çevrimdışı dönemlerde olayları kuyruğa alır ve çevrimiçi olduğunda senkronize olur  
- Denetim Günlüğü: Sistemdeki tüm eylemler için kapsamlı denetim izi  
- Rol Hazır Mimari: Rol tabanlı erişim kontrolü (RBAC) desteklemek üzere tasarlandı  

### Yığın
- Arka uç: FastAPI, SQLAlchemy, Pydantic  
- Ön uç: React, TypeScript, Vite  
- Edge Ajan Simülatörü: Python  

### Kurulum & Kullanım
**Ön Koşullar**  
- Docker ve Docker Compose  
- (İsteğe bağlı) Üretim dağıtımı için Kubernetes kümesi  

**Docker Compose ile Çalıştırma**  
1. Depoyu klonlayın  
2. Proje dizinine gidin  
3. Örnek ortam dosyasını kopyalayın: `cp backend/.env.example backend/.env`  
4. Gerekiyorsa `.env` dosyasını düzenleyin (PostgreSQL bağlantısı için)  
5. Hizmetleri başlatın: `make up`  
6. Kontrol panelini http://localhost:3000 adresinden erişin  
7. Arka uç API'si http://localhost:8000 adresinde kullanılabilir  

**Kubernetes ile Çalıştırma**  
1. Veritabanı depolama sınıfı ve PVC'yi uygulayın (zaten mevcut değilse)  
2. Kubernetes bildirimlerini uygulayın: `kubectl apply -f kubernetes/`  
3. Frontend'e LoadBalancer hizmeti üzerinden veya bir Ingress kurarak erişin  

**Örnek Veri**  
Veritabanına örnek veri doldurmak için örnek veri betiğini çalıştırın:  
- Docker Compose: `docker-compose run --rm backend python kubernetes/scripts/sample_data.py`  
- Kubernetes: `kubectl run --rm -i --tty sample-data --image=edgesentinel-backend:latest --restart=Never -- python kubernetes/scripts/sample_data.py`  

### Test
- Arka uç: `make test` komutu ile arka uç testlerini çalıştırın  
- Ön uç: `make frontend` komutu ön uç geliştirme modunu başlatır  
- Edge Ajan Simülatörü: Belirli bir test komutu belgelenmemiştir  

### Sınırlamalar
README'de açıkça belirtilen bir sınırlama bulunmamaktadır.

### Lisans
Bu proje özel ve gizlidir. Tüm hakları saklıdır.

## Deutsch

### Zweck
EdgeSentinel ist ein umfassendes Portfolio-Produkt zur Verwaltung von Flotten von Edge AI Vision Geräten. Es bietet Geräteregistrierung, Heartbeat-Überwachung, Kamera-Stream-Simulation, Modelleregister mit unveränderlichen Versionen und Rollout-Zuständen, Inferenz-Ereignisaufnahme, Alarmbestätigung, menschlichen Review/Feedback-Schleife, Drift-Metriken-Berechnung, Offline-Edge-Warteschlange mit Wiederholungs-/Sync-Verhalten, Audit-Protokoll und rollenbereite Architektur.

### Funktionen
- Geräteverwaltung: Registrieren und Überwachen von Edge-Geräten über Heartbeats  
- Modelleregister: Speichern und Verwalten von KI-Modellversionen mit Unveränderlichkeitsflags und Rollout-Zuständen  
- Ereignisaufnahme: Empfangen und Verarbeiten von Inferenzereignissen von Edge-Geräten  
- Alarmierung: Erzeugung von Alarmen basierend auf Drift, niedrigem Konfidenzwert oder Anomalien  
- Menschliche Überprüfung: Workflow für menschliches Feedback zu Inferenzen  
- Drift-Erkennung: Berechnung von Drift-Metriken aus Ereigniskonfidenz und Feature-Statistiken  
- Offline-Unterstützung: Der Edge-Agent stellt Ereignisse während Offline-Perioden in einer Warteschlange bereit und synchronisiert, wenn er wieder online ist  
- Audit-Protokoll: Umfassender Audit-Trail für alle Systemaktionen  
- Rollenbereite Architektur: Ausgelegt zur Unterstützung von rollenbasierter Zugriffskontrolle (RBAC)  

### Stack
- Backend: FastAPI, SQLAlchemy, Pydantic  
- Frontend: React, TypeScript, Vite  
- Edge-Agent-Simulator: Python  

### Einrichtung & Nutzung
**Voraussetzungen**  
- Docker und Docker Compose  
- (Optional) Kubernetes-Cluster für Produktionsbereitstellung  

**Ausführung mit Docker Compose**  
1. Repository klonen  
2. In das Projektverzeichnis wechseln  
3. Beispiel-Umgebungsdatei kopieren: `cp backend/.env.example backend/.env`  
4. Bei Bedarf die `.env` Datei bearbeiten (für PostgreSQL-Verbindung)  
5. Dienste starten: `make up`  
6. Dashboard unter http://localhost:3000 aufrufen  
7. Das Backend-API ist unter http://localhost:8000 verfügbar  

**Ausführung mit Kubernetes**  
1. Datenbank-Speicherklasse und PVC anwenden (falls noch nicht vorhanden)  
2. Kubernetes-Manifests anwenden: `kubectl apply -f kubernetes/`  
3. Frontend über den LoadBalancer-Dienst zugreifen oder ein Ingress einrichten  

**Beispieldaten**  
Um die Datenbank mit Beispieldaten zu füllen, das Beispieldatenskript ausführen:  
- Docker Compose: `docker-compose run --rm backend python kubernetes/scripts/sample_data.py`  
- Kubernetes: `kubectl run --rm -i --tty sample-data --image=edgesentinel-backend:latest --restart=Never -- python kubernetes/scripts/sample_data.py`  

### Tests
- Backend: Führe `make test` aus, um Backend-Tests auszuführen  
- Frontend: `make frontend` startet den Frontend im Entwicklungsmodus  
- Edge-Agent-Simulator: Kein spezifischer Testbefehl dokumentiert  

### Einschränkungen
Im README sind keine expliziten Einschränkungen dokumentiert.

### Lizenz
Dieses Projekt ist proprietär und vertraulich. Alle Rechte vorbehalten.
