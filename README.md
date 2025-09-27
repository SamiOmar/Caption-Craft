# Caption Craft Website

Eine moderne, responsive Website für die Caption Craft iOS App - die ultimative Lösung für automatische Video-Untertitel.

## 🌟 Features

- **Responsive Design**: Optimiert für alle Geräte (Desktop, Tablet, Mobile)
- **Moderne UI/UX**: Sauberes, professionelles Design mit iOS-inspirierter Ästhetik
- **Interaktive Elemente**: FAQ-Accordion, mobile Navigation, smooth scrolling
- **SEO-optimiert**: Meta-Tags, strukturierte Daten, semantisches HTML
- **Performance**: Optimierte Bilder, CSS und JavaScript
- **Accessibility**: WCAG-konform, tastaturnavigierbar

## 📁 Dateistruktur

```
caption-craft-website/
├── index.html          # Hauptseite
├── privacy.html        # Datenschutzerklärung
├── terms.html          # Allgemeine Geschäftsbedingungen
├── styles.css          # Haupt-Stylesheet
├── script.js           # JavaScript-Funktionalität
├── README.md           # Diese Datei
└── images/             # Bilder-Ordner (zu erstellen)
    ├── app-icon.png
    ├── app-screenshot-main.png
    ├── screenshot-1.png
    ├── screenshot-2.png
    ├── screenshot-3.png
    ├── screenshot-4.png
    ├── screenshot-5.png
    ├── step-1.png
    ├── step-2.png
    ├── step-3.png
    ├── og-image.jpg
    ├── apple-touch-icon.png
    └── app-store-badge.svg
```

## 🚀 GitHub Pages Setup

### 1. Repository erstellen
```bash
# Navigiere zu deinem Website-Ordner
cd "/Users/sami/Caption Craft webseite"

# Git initialisieren
git init

# Remote Repository hinzufügen (ersetze USERNAME mit deinem GitHub-Username)
git remote add origin https://github.com/USERNAME/caption-craft-website.git

# Erste Commits
git add .
git commit -m "Initial website setup"
git push -u origin main
```

### 2. GitHub Pages aktivieren
1. Gehe zu deinem GitHub Repository
2. Klicke auf "Settings"
3. Scrolle zu "Pages" im linken Menü
4. Wähle "Deploy from a branch"
5. Wähle "main" als Branch
6. Klicke "Save"

### 3. Custom Domain (optional)
Wenn du eine eigene Domain hast:
1. Erstelle eine Datei namens `CNAME` mit deiner Domain
2. Konfiguriere DNS-Einstellungen bei deinem Domain-Provider

## 📱 Benötigte Bilder

Du musst folgende Bilder erstellen und im `images/` Ordner speichern:

### App-Bilder
- `app-icon.png` (512x512px) - App-Icon
- `app-screenshot-main.png` (750x1334px) - Haupt-Screenshot für Hero-Sektion

### Screenshots (375x812px iPhone-Format)
- `screenshot-1.png` - Hauptbildschirm
- `screenshot-2.png` - Video Upload
- `screenshot-3.png` - Transkription
- `screenshot-4.png` - Untertitel Editor
- `screenshot-5.png` - Style Auswahl

### How-it-works Bilder (600x400px)
- `step-1.png` - Video auswählen
- `step-2.png` - Transkription
- `step-3.png` - Export

### Meta-Bilder
- `og-image.jpg` (1200x630px) - Social Media Sharing
- `apple-touch-icon.png` (180x180px) - iOS Home Screen Icon

### App Store Badge
- `app-store-badge.svg` - "Download im App Store" Button

## 🎨 Anpassungen

### Farben ändern
In `styles.css` unter `:root` oder in der `.btn-primary` Klasse:
```css
:root {
    --primary-color: #007AFF;  /* Deine Hauptfarbe */
    --secondary-color: #0056b3; /* Deine Sekundärfarbe */
}
```

### App Store Link aktualisieren
In `index.html` finde und ersetze:
```html
<a href="https://apps.apple.com/app/caption-craft/idXXXXXXXXX"
```
mit deiner echten App Store URL.

### Contact Information
Ersetze alle E-Mail-Adressen:
- `support@captioncraft.app`
- `privacy@captioncraft.app`
- `legal@captioncraft.app`

mit deinen echten E-Mail-Adressen.

## 📊 Analytics Setup

### Google Analytics hinzufügen
Füge in `<head>` von `index.html` hinzu:
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_TRACKING_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_TRACKING_ID');
</script>
```

## 🔧 Performance Optimierung

### Bilder komprimieren
Nutze Tools wie:
- TinyPNG für PNG-Dateien
- ImageOptim für allgemeine Komprimierung
- WebP-Format für bessere Performance

### CDN nutzen
Für bessere Performance kannst du Bilder über ein CDN laden.

## 📝 SEO Checklist

- [x] Title Tags optimiert
- [x] Meta Descriptions hinzugefügt
- [x] Open Graph Tags für Social Media
- [x] Strukturierte Daten
- [x] Alt-Texte für Bilder
- [x] Semantisches HTML
- [x] Mobile-friendly
- [x] Schnelle Ladezeiten

## 🛠 Wartung

### Regelmäßige Updates
- Screenshots aktualisieren bei App-Updates
- Datenschutzerklärung und AGB bei Änderungen aktualisieren
- Broken Links prüfen
- Performance überwachen

### Backup
Erstelle regelmäßig Backups:
```bash
git add .
git commit -m "Update: [Beschreibung der Änderungen]"
git push
```

## 🆘 Support

Bei Problemen oder Fragen:
1. Prüfe die GitHub Pages Dokumentation
2. Validiere HTML/CSS mit W3C Validators
3. Teste auf verschiedenen Geräten und Browsern

## 📄 Lizenz

Diese Website ist für die Caption Craft App erstellt. Alle Rechte vorbehalten.

---

**Happy Coding!** 🚀

Deine Website ist jetzt bereit für GitHub Pages. Vergiss nicht, die Bilder hinzuzufügen und die Links zu personalisieren!