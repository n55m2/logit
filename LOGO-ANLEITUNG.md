# 🎨 Logo einbauen - Anleitung

Diese Anleitung zeigt dir, wie du dein Logit Computer GmbH Logo in die Website einbaust.

## Schnellstart

### Schritt 1: Logo-Datei vorbereiten

Speichere dein Logo in einem dieser Formate:
- **PNG** (empfohlen für Logos mit transparentem Hintergrund)
- **SVG** (beste Qualität, skaliert perfekt)
- **JPG** (falls kein Transparenz benötigt wird)

**Empfohlene Größe**: Mindestens 120px Breite, 40-50px Höhe

### Schritt 2: Logo in den Ordner kopieren

Kopiere deine Logo-Datei in den gleichen Ordner wie `index.html` und benenne sie:
- `logo.png` ODER
- `logo.svg` ODER
- `logo.jpg`

### Schritt 3: HTML anpassen

Öffne `index.html` und finde Zeile **18-24** (Navigation):

```html
<div class="logo">
    <!-- Logo Option 1: Ersetze mit deinem Logo-Bild -->
    <!-- <img src="logo.png" alt="Logit Computer GmbH Logo" class="logo-image"> -->

    <!-- Logo Option 2: Aktuell - Text Logo -->
    <h1>Logit<span class="highlight">.</span></h1>
</div>
```

**Ändere zu:**

```html
<div class="logo">
    <!-- Logo mit Bild -->
    <img src="logo.png" alt="Logit Computer GmbH Logo" class="logo-image">
</div>
```

### Schritt 4: (Optional) Footer-Logo anpassen

Finde Zeile **269-275** (Footer):

```html
<div class="footer-logo">
    <!-- Optional: Ersetze mit Logo-Bild -->
    <img src="logo.png" alt="Logit Logo" class="footer-logo-image">

    <h3>Logit<span class="highlight">.</span></h3>
    <p>Ihr Partner für professionelle IT-Lösungen</p>
</div>
```

## Erweiterte Optionen

### Option A: Logo + Text kombiniert

```html
<div class="logo" style="display: flex; align-items: center; gap: 12px;">
    <img src="logo.png" alt="Logit Logo" class="logo-image">
    <h1 style="margin: 0;">Logit</h1>
</div>
```

### Option B: SVG-Logo direkt einbetten

```html
<div class="logo">
    <svg width="120" height="40" viewBox="0 0 120 40">
        <!-- Füge hier deinen SVG-Code ein -->
    </svg>
</div>
```

### Option C: Logo-Größe anpassen

Falls dein Logo größer/kleiner sein soll, füge in `styles.css` hinzu:

```css
.logo-image {
    height: 50px;  /* Ändere die Höhe nach Bedarf */
    width: auto;
}
```

## Logo-Farbe passend machen

### Für weißes Logo auf dunklem Hintergrund (Footer):

Das Footer-Logo wird automatisch weiß gefärbt durch:
```css
.footer-logo-image {
    filter: brightness(0) invert(1);
}
```

Falls dein Logo schon weiß ist oder die Farbe #f23568 haben soll, entferne diese Zeile.

### Logo mit #f23568 einfärben (nur bei einfarbigen SVGs):

```css
.logo-image {
    filter: brightness(0) saturate(100%) invert(37%) sepia(91%)
            saturate(3451%) hue-rotate(323deg) brightness(97%) contrast(94%);
}
```

## Häufige Probleme

### Problem: Logo wird nicht angezeigt
**Lösung**: Prüfe ob:
- Die Logo-Datei im richtigen Ordner ist
- Der Dateiname korrekt ist (Groß-/Kleinschreibung beachten!)
- Der Pfad in `src="logo.png"` stimmt

### Problem: Logo ist zu groß/klein
**Lösung**: Ändere die `height` in `.logo-image` in der `styles.css`:
```css
.logo-image {
    height: 40px;  /* Ändere diesen Wert */
}
```

### Problem: Logo hat falsche Farbe
**Lösung**: Entferne die `filter` Eigenschaft oder passe sie an

## Dateistruktur

Nach dem Logo-Einbau sollte dein Ordner so aussehen:

```
logit-website/
├── index.html
├── styles.css
├── script.js
├── logo.png          ← Dein Logo hier
├── LOGO-ANLEITUNG.md
└── README.md
```

## Testen

1. Öffne `index.html` in deinem Browser
2. Das Logo sollte oben links in der Navigation sichtbar sein
3. Beim Scrollen bleibt es fixiert oben

## Farben der Website

Die Website verwendet jetzt eure Corporate Color:
- **Hauptfarbe**: #f23568 (Pink/Magenta aus dem Logo)
- **Dunklere Variante**: #d12050
- **Hellere Variante**: #f5517d

Diese Farbe wird verwendet für:
- Buttons
- Links (beim Hover)
- Icons
- Highlights

---

**Brauchst du Hilfe?** Die Logo-Styles findest du in `styles.css` ab Zeile 101.
