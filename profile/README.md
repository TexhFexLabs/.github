# Status
[![Build & Deploy Angular Frontend](https://github.com/TexhFexLabs/frontendWS/actions/workflows/build-and-deploy.yml/badge.svg)](https://github.com/TexhFexLabs/frontendWS/actions/workflows/build-and-deploy.yml)
[![Build & Deploy Webhook Service](https://github.com/TexhFexLabs/helium-webhook-handler/actions/workflows/deploy.yml/badge.svg)](https://github.com/TexhFexLabs/helium-webhook-handler/actions/workflows/deploy.yml)
[![Build & Deploy Backend Service](https://github.com/TexhFexLabs/backend/actions/workflows/build-and-deploy.yml/badge.svg)](https://github.com/TexhFexLabs/backend/actions/workflows/build-and-deploy.yml)

[![frontend build and deploy](https://github.com/TexhFexLabs/mtp-frontend/actions/workflows/frontend.yml/badge.svg)](https://github.com/TexhFexLabs/mtp-frontend/actions/workflows/frontend.yml)
[![backend build and deploy](https://github.com/TexhFexLabs/mtp-backend/actions/workflows/backend.yml/badge.svg)](https://github.com/TexhFexLabs/mtp-backend/actions/workflows/backend.yml)
# Texhfexlabs.de
Info folgt.

# meintennisplatz.de
Digitalisiere deinen Tennisplatz für eine schnelle und unkomplizierte Buchung deines Spielerlebnisses.
https://meintennisplatz.de

![Landing Page](https://github.com/TexhFex/meintennisplatz.de/assets/60287876/d6d2677b-edf8-4b6e-bb08-ecc3fdc1d4e4)


## Einführung
Dieses Dokument bietet eine Übersicht über die Architektur und die technologischen Entscheidungen, die für die Implementierung des Tennisplatzbuchungssystems getroffen wurden. Das System nutzt moderne Cloud-Native Technologien und Frameworks, um eine skalierbare, wartbare und effiziente Anwendung zu gewährleisten.

### Architekturübersicht
Das System setzt auf eine Microservices-Architektur, die in Kubernetes auf DigitalOcean (DOKS) gehostet wird. Die Verwendung von Kubernetes ermöglicht es, dynamisch auf Laständerungen zu reagieren, indem Pods automatisch hinzugefügt oder entfernt werden, um die Nachfrage zu bedienen. Ein Ingress Controller leitet den externen Verkehr an die entsprechenden Services im Cluster weiter.

#### Backend
Das Backend basiert auf Quarkus, einem Kubernetes-nativen Java-Framework, das für seine effiziente Ausführung in Container-Umgebungen optimiert ist. Quarkus minimiert den Speicherbedarf und verbessert die Startzeit, was es ideal für Microservices macht, die in einem sich selbst skalierenden Kubernetes-Cluster laufen.

##### Vorteile von Quarkus:
- **Container-First**: Entwickelt für Container und Kubernetes, bietet Quarkus eine nahtlose Erfahrung in Cloud-Native Umgebungen.
- **Reaktive Programmierung**: Unterstützt ein nicht-blockierendes I/O-Modell, das die Systemeffizienz und Skalierbarkeit verbessert.
- **Entwicklerproduktivität**: Live-Reload-Fähigkeiten und eine umfangreiche Sammlung von Erweiterungen beschleunigen die Entwicklung.

#### Frontend
Das Frontend wird mit Angular entwickelt, einem leistungsfähigen Framework für den Bau von Single-Page-Anwendungen (SPA). Angular bietet eine reichhaltige Menge an Funktionen und Tools, die die Entwicklung von komplexen, reaktiven Benutzeroberflächen vereinfachen.

##### Style und Komponenten
Für das Styling und UI-Komponenten wird PrimeFaces Apollo NG verwendet, ein hochwertiges Template, das speziell für Angular entwickelt wurde. Dies ermöglicht es, konsistente und ansprechende Benutzeroberflächen mit minimalen Aufwand zu erstellen.

### CI/CD und Deployment
Der Continuous Integration und Deployment-Prozess ist vollständig automatisiert. Sowohl das Backend als auch das Frontend werden in Docker-Container gebaut und in das Digital Ocean Container Registry gepusht. Anschließend werden die Kubernetes-Pods über Rolling Updates neu gestartet, um die neuen Images zu laden, was eine nahtlose Aktualisierung der Anwendung mit minimaler Downtime ermöglicht.

#### Prozessablauf:
1. **Build und Test**: Bei jedem Commit werden das Backend und das Frontend gebaut und getestet.
2. **Docker Image Erstellung**: Nach erfolgreichem Build wird für jede Komponente ein Docker Image erstellt.
3. **Push ins Registry**: Die erstellten Docker Images werden in das Digital Ocean Container Registry gepusht.
4. **Deployment**: Kubernetes-Pods werden automatisch aktualisiert, um die neuen Images zu verwenden.

### Zusammenfassung
Das Tennisplatzbuchungssystem nutzt eine Kombination aus modernen Technologien und Frameworks, um eine skalierbare, effiziente und wartbare Anwendung zu gewährleisten. Die Verwendung von Kubernetes, Quarkus, Angular und PrimeFaces Apollo NG stellt sicher, dass das System den Anforderungen moderner Cloud-Native Anwendungen gerecht wird und sich leicht an zukünftige Anforderungen anpassen lässt.

### Sicherheit

Die gesamte Kommunikation läuft über ein Wildcard-Zertifikat von IONOS, verwaltet durch einen Production-Zertifikat-Controller in Kubernetes über Let's Encrypt. Dies gewährleistet eine sichere und verschlüsselte Verbindung für alle Nutzer der Plattform.

### Monitoring

Zur Überwachung der Server und zur Sicherstellung der Online-Verfügbarkeit von meintennisplatz.de wird [Xitoring](https://app.xitoring.com/ui/dashboard) verwendet. Dieses Tool ermöglicht eine umfassende Überwachung und bietet Echtzeit-Alerts, um die Verfügbarkeit der Plattform zu maximieren.

### Roadmap

- **Kurzfristig:**
  - Refactoring des Backends für verbesserte Wartbarkeit und Skalierbarkeit.
  - Integration eines Club Control Modal Mockups mit Backend-Unterstützung.

- **Mittelfristig:**
  - Entwicklung eines Admin-Panels zur vereinfachten Verwaltung der Plattform.

Die Roadmap konzentriert sich darauf, das Fundament der Plattform zu stärken und gleichzeitig neue Funktionalitäten zu integrieren, um den Nutzern ein nahtloses Erlebnis zu bieten.

### Über den Entwickler

Dieses Projekt wurde mit Leidenschaft und Sorgfalt von Felix Knoll entwickelt, um Tennisvereinen und ihren Mitgliedern eine moderne und effiziente Lösung zur Platzbuchung zu bieten. Es ist das Ergebnis umfangreicher Forschung und Entwicklungsarbeit im Bereich der Webtechnologien.
