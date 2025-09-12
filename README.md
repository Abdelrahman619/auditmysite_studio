# AuditMySite Studio

<p align="center">
  <img src="https://img.shields.io/badge/Status-Early_Alpha-orange" alt="Status: Early Alpha">
  <img src="https://img.shields.io/badge/Platform-macOS%20%7C%20Windows-blue" alt="Platform: macOS | Windows">
  <img src="https://img.shields.io/badge/Framework-Flutter_Desktop-blue" alt="Framework: Flutter Desktop">
  <img src="https://img.shields.io/badge/Engine-Dart-blue" alt="Engine: Dart">
</p>

A comprehensive **desktop application** for website auditing, built with Flutter for **macOS and Windows**. This is a **Dart port** of the [original AuditMySite project](https://github.com/casoon/auditmysite) with the goal of **feature parity** and native desktop experience.

> ⚠️ **Early Alpha Stage**: This project is currently in active development and should be considered experimental.

## 🎯 Project Goals

- **Desktop-first**: Native macOS and Windows applications
- **Feature Parity**: Match capabilities with the [original AuditMySite project](https://github.com/casoon/auditmysite)
- **Professional UI**: Modern, responsive Flutter desktop interface  
- **Comprehensive Audits**: 6 audit categories with detailed scoring
- **Real-time Progress**: Live WebSocket updates during audits

## ✨ Current Features (v0.1-alpha)

### 🔧 **Audit Engine** (Dart)
- **HTTP Analysis**: Status codes, headers, redirects, SSL, response times
- **Performance Audits**: Core Web Vitals (TTFB, FCP, LCP, CLS) with A-F scoring
- **SEO Audits**: Meta tags, headings, images, OpenGraph, Twitter Cards
- **Content Weight**: Resource analysis, optimization recommendations
- **Mobile Friendliness**: Responsive design, touch targets, viewport
- **Accessibility**: Axe-core integration for WCAG compliance

### 🖥️ **Desktop Application** (Flutter)
- **Responsive UI**: Adaptive layouts for different window sizes
- **Live Engine Status**: Real-time connection monitoring
- **Audit Configuration**: Flexible settings for all audit categories
- **Progress Tracking**: WebSocket-based live updates
- **Results Management**: JSON export with detailed grading

## 🏗️ Architecture

```
auditmysite_studio/
├── auditmysite_engine/     # Dart audit engine (HTTP API + WebSocket)
├── auditmysite_studio/     # Flutter desktop application  
├── auditmysite_cli/        # Command-line interface
└── shared/                 # Shared models and utilities
```

### **Engine Features**:
- REST API for audit management
- WebSocket for real-time progress
- Puppeteer-based browser automation
- Sitemap parsing and URL discovery
- Concurrent processing with rate limiting

### **Desktop App Features**:
- Native macOS/Windows experience  
- NavigationRail for desktop layouts
- Minimum window size enforcement (900×700)
- Responsive breakpoints (<800px mobile, ≥800px desktop)
- Material Design 3 with consistent branding

## 🚀 Quick Start

### Prerequisites
- Flutter SDK (≥3.19.0)
- Dart SDK (≥3.3.0) 
- Chrome/Chromium (for Puppeteer)

### Development Setup
```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/auditmysite-studio.git
cd auditmysite-studio

# Install dependencies
flutter pub get
cd auditmysite_engine && dart pub get

# Start the audit engine
cd auditmysite_engine
dart run bin/serve.dart --port 8080

# Start the Flutter desktop app (in another terminal)
cd auditmysite_studio  
flutter run -d macos  # or -d windows
```

### Using the Application
1. **Start Engine**: The audit engine provides the backend API
2. **Launch Desktop App**: Flutter app connects automatically to engine
3. **Configure Audit**: Set sitemap URL and select audit categories
4. **Run Audit**: Monitor progress in real-time via WebSocket
5. **View Results**: Detailed JSON reports with A-F grading

## 📊 Audit Categories

| Category | Features | Scoring |
|----------|----------|----------|
| **HTTP** | Status codes, redirects, SSL, headers | Info only |
| **Performance** | Core Web Vitals, optimization tips | A-F Grade |
| **SEO** | Meta tags, headings, structured data | A-F Grade |
| **Content Weight** | Resource sizes, loading optimization | A-F Grade |
| **Mobile Friendliness** | Responsive design, touch targets | A-F Grade |
| **Accessibility** | WCAG violations, axe-core analysis | Info only |

## 🎨 Screenshots

### Desktop Application (macOS)
- **Setup View**: Configure audits with modern, responsive UI
- **Progress View**: Real-time audit progress with WebSocket updates
- **Results View**: Detailed findings with actionable recommendations
- **Settings View**: Engine configuration and preferences

*(Screenshots will be added as the project matures)*

## 🚧 Development Status

### ✅ **Completed** (Early Alpha)
- [x] Dart audit engine with 6 categories
- [x] Flutter desktop application (macOS/Windows)
- [x] HTTP API with WebSocket support
- [x] Responsive UI with adaptive navigation
- [x] Real-time progress monitoring
- [x] JSON export with detailed scoring

### 🔄 **In Progress**
- [ ] Results visualization and charts
- [ ] Audit history and comparison
- [ ] Export formats (PDF, CSV)
- [ ] Advanced settings and configuration
- [ ] Performance optimizations

### 📋 **Planned**
- [ ] Feature parity with [original project](https://github.com/casoon/auditmysite)
- [ ] Signed macOS and Windows distributions
- [ ] Auto-update mechanism
- [ ] Plugin architecture for custom audits
- [ ] Batch processing and scheduling

## 🤝 Relationship to Original Project

This project is a **Dart/Flutter port** of [casoon/auditmysite](https://github.com/casoon/auditmysite) with these key differences:

- **Technology**: Dart/Flutter instead of original stack
- **Platform**: Desktop applications (macOS/Windows) as primary target
- **Architecture**: Modular design with separate engine and UI components
- **Goal**: Feature parity while leveraging Flutter's cross-platform capabilities

Both projects aim to provide comprehensive website auditing capabilities, with this version focusing on native desktop experience.

## 📋 Release Strategy

### Distribution Model
- **Manual Creation**: Applications will be manually built and signed
- **Platform-specific**: Native macOS (.app) and Windows (.exe) packages
- **Code Signing**: Applications will be properly signed for distribution
  - macOS: Developer ID Application certificate
  - Windows: Code signing certificate for trusted installation

### Versioning
- **Current**: v0.1-alpha (Early development)
- **Target**: v1.0 (Feature parity with original project)
- **Semantic Versioning**: Following semver.org conventions

## 🛠️ Development

### Contributing
This project is currently in early development. Contribution guidelines will be established as the project stabilizes.

### Building for Distribution

#### macOS
```bash
flutter build macos --release
# Code signing will be handled separately
```

#### Windows  
```bash
flutter build windows --release
# Code signing will be handled separately
```

## 📄 License

MIT License - see [LICENSE](LICENSE) file for details.

## 🙋‍♂️ Support

- **Issues**: [GitHub Issues](https://github.com/YOUR_USERNAME/auditmysite-studio/issues)
- **Discussions**: [GitHub Discussions](https://github.com/YOUR_USERNAME/auditmysite-studio/discussions)
- **Original Project**: [casoon/auditmysite](https://github.com/casoon/auditmysite)

---

**Built with ❤️ using Flutter and Dart**

> This project is part of the broader AuditMySite ecosystem, providing desktop-native website auditing capabilities.

# auditmysite_studio

Ein umfassendes Website-Audit-System mit drei Hauptkomponenten:

- **auditmysite_engine** (Dart): Lädt Sitemaps, führt Audits per CDP + axe-core aus
- **auditmysite_cli** (Dart): Erstellt HTML-Reports aus JSON-Artefakten  
- **auditmysite_studio** (Flutter Desktop): GUI für Endanwender

## Architektur

```
auditmysite_studio/
├─ shared/                    # gemeinsame Modelle & Utils
├─ auditmysite_engine/        # Dart-Engine (Sitemap → Queue → CDP + axe)
├─ auditmysite_cli/           # CLI: JSON → HTML-Report
└─ auditmysite_studio/        # Flutter Desktop GUI
```

## Quick Start

### 1. Setup

Stelle sicher, dass Du Dart ≥3.3.0 und Flutter ≥3.19.0 installiert hast.

```bash
# Root-Verzeichnis
cd auditmysite_studio

# Shared-Modelle generieren
cd shared
dart pub get
dart run build_runner build --delete-conflicting-outputs
cd ..

# Dependencies für alle Packages installieren
cd auditmysite_engine && dart pub get && cd ..
cd auditmysite_cli && dart pub get && cd ..
cd auditmysite_studio && flutter pub get && cd ..
```

### 2. axe-core Integration

Die echte `axe.min.js` Datei muss von [axe-core](https://github.com/dequelabs/axe-core) heruntergeladen werden:

```bash
# Download der aktuellen axe-core Version
wget https://cdnjs.cloudflare.com/ajax/libs/axe-core/4.8.4/axe.min.js \
  -O auditmysite_engine/third_party/axe/axe.min.js
```

### 3. Engine ausführen

**Standard Modus:**
```bash
cd auditmysite_engine
dart run bin/run.dart \
  --sitemap=https://example.com/sitemap.xml \
  --out=./artifacts \
  --concurrency=4 \
  --perf \
  --screenshots
```

**Mit Live WebSocket (Sprint 2):**
```bash
cd auditmysite_engine
dart run bin/run.dart \
  --serve \
  --sitemap=https://example.com/sitemap.xml \
  --out=./artifacts \
  --concurrency=4 \
  --perf
```

**Nur WebSocket Server:**
```bash
cd auditmysite_engine
dart run bin/serve.dart --port=8080
```

Dies erstellt JSON-Dateien in `./artifacts/<runId>/pages/`.

### 4. HTML-Report generieren

```bash
cd auditmysite_cli
dart run bin/build.dart \
  --in=../auditmysite_engine/artifacts/<runId>/pages \
  --out=./reports \
  --title="Website Audit"
```

Öffne dann `./reports/index.html` im Browser.

### 5. GUI starten

```bash
cd auditmysite_studio
flutter run -d macos  # oder windows/linux
```

## Features

### Engine Features
- ✅ Sitemap-Parsing (inkl. sitemap index)
- ✅ Concurrent Processing mit konfigurierbaren Workern
- ✅ HTTP-Status und Header-Erfassung
- ✅ Performance-Metriken (TTFB, FCP, LCP, DCL)
- ✅ Accessibility-Audits mit axe-core
- ✅ Console Error-Sammlung
- ✅ Optional: Full-Page Screenshots
- ✅ Event-System für Live-Tracking

### CLI Features  
- ✅ JSON zu HTML-Konvertierung
- ✅ Übersichts-Report mit Tabelle aller Seiten
- ✅ Detail-Seiten pro URL
- ✅ Performance-Metriken Visualization
- ✅ Accessibility Violations mit Impact-Level
- ✅ Console Errors Darstellung

### Studio Features (Sprint 2)
- ✅ Run-Setup Interface
- ✅ Manual Command Generation  
- ✅ Live Progress Tracking via WebSocket
- ✅ Results Loading & Management
- ✅ Interactive Data Table with Statistics
- 😧 Integrated Report Generation (Sprint 3)

## Nächste Schritte

### Sprint 2 ✅ COMPLETE
- ✅ WebSocket-Integration für Live-Events  
- ✅ Retry/Backoff-Mechanismus in der Engine
- ✅ Results Loading in der Studio-App
- ✅ Enhanced CLI Template-System mit Filter/Suche
- ✅ Performance-Metriken Sammlung

### Sprint 3  
- [ ] Engine Performance-Metriken (CPU/RAM)
- [ ] CLI Template-System auslagern
- [ ] Filter/Suche im HTML-Report
- [ ] Studio Export-Integration

### Sprint 4
- [ ] robots.txt Respektierung
- [ ] Auth/Cookies Support
- [ ] Mobile/Device-Profile Emulation
- [ ] Projektverwaltung & Persistenz

## JSON Schema

Jede Seite wird als JSON-Datei nach folgendem Schema gespeichert:

```json
{
  "schemaVersion": "1.0.0",
  "runId": "2024-01-15T10-30-00",
  "url": "https://example.com/page",
  "http": {
    "statusCode": 200,
    "headers": {...}
  },
  "perf": {
    "ttfbMs": 120.5,
    "fcpMs": 890.2,
    "lcpMs": 1240.8,
    "domContentLoadedMs": 1100.0,
    "loadEventEndMs": 1250.0,
    "engine": {
      "cpuUserMs": 45.2,
      "cpuSystemMs": 12.1,
      "peakRssBytes": 125829120,
      "taskDurationMs": 2340.5
    }
  },
  "a11y": {
    "violations": [...]
  },
  "consoleErrors": [...],
  "screenshotPath": "artifacts/screenshots/...",
  "startedAt": "2024-01-15T10:30:01.000Z",
  "finishedAt": "2024-01-15T10:30:03.340Z"
}
```

## Lizenz

MIT License - siehe todo.md für weitere Details zur Implementierung.
