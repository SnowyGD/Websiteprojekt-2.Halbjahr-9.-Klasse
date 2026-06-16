# Kategorie-Navigations-System - Erklärung

## Wie das System funktioniert

### 1. **Die Sidebar (Linke Seite)**
- Die Sidebar ist ein festes Menü, das auf der linken Seite bleibt, während man scrollt
- Es enthält Buttons für alle 8 Kategorien
- **CSS-Eigenschaft:** `position: fixed` hält die Sidebar an einer Position

### 2. **Wie die Sortierung funktioniert - 2 Teile:**

#### Teil A: HTML-Struktur
```
Jede Kategorie hat eine ID:
<h2 class="category-heading" id="magnolien">Magnolien</h2>

Die Sidebar-Buttons verlinken zu diesen IDs:
<a href="#magnolien" class="category-button">Magnolien</a>
```

**Erklärung:**
- `id="magnolien"` = eindeutige Bezeichnung für diese Sektion
- `href="#magnolien"` = der Link zeigt auf die Section mit dieser ID
- Das `#` Symbol bedeutet "Springe zu dieser Stelle auf der Seite"

#### Teil B: CSS für das Layout
```css
body {
    margin-left: 200px;  /* Platz für die Sidebar */
}

.sidebar {
    position: fixed;     /* Bleibt an einer Stelle */
    width: 180px;        /* Breite der Sidebar */
    height: 100vh;       /* Volle Bildschirmhöhe */
    left: 0;            /* Am linken Rand */
}
```

### 3. **Was passiert wenn man auf einen Button klickt?**

1. Benutzer klickt auf "Rosen" Button
2. Der Browser sieht: `href="#rosen"`
3. Der Browser sucht: `id="rosen"` auf der Seite
4. Der Browser springt zu dieser Stelle
5. Die Sidebar bleibt sichtbar (weil sie fixed ist)
6. Der Inhalt scrollt unter der Sidebar

### 4. **Die 8 Kategorien:**

| Kategorie | ID | Speicherort |
|-----------|-----|-----------|
| Magnolien | `#magnolien` | Zeile 98 |
| Kräuter & Grünpflanzen | `#kraeuter` | Zeile 138 |
| Tulpen | `#tulpen` | Zeile 176 |
| Rosen | `#rosen` | Zeile 250 |
| Frühlingsblumen | `#fruehling` | Zeile 324 |
| Sommerblumen | `#sommer` | Zeile 362 |
| Schnittblumen | `#schnitt` | Zeile 436 |
| Sträuße | `#strauesse` | Zeile 474 |

### 5. **Vorteile dieses Systems:**

✅ **Nur HTML & CSS** - kein JavaScript nötig
✅ **Schnell** - Links funktionieren sofort
✅ **Responsive** - funktioniert auf allen Geräten
✅ **SEO-freundlich** - Browser und Suchmaschinen verstehen die Links
✅ **Einfach zu erweitern** - einfach neue Kategorien hinzufügen

### 6. **Wie man neue Kategorien hinzufügt:**

**Schritt 1:** Neue ID zur Kategorie hinzufügen
```html
<h2 class="category-heading" id="neue-kategorie">Neue Kategorie</h2>
```

**Schritt 2:** Button zur Sidebar hinzufügen
```html
<a href="#neue-kategorie" class="category-button">Neue Kategorie</a>
```

**Fertig!** Der Button funktioniert automatisch.

## Technische Details

### Position: Fixed
- Element bleibt immer an der gleichen Position im Fenster
- Scrollt nicht mit der Seite
- Gut für Navigationsmenüs

### Anchors (#)
- `href="#id"` springt zu Element mit `id="id"`
- Funktioniert ohne JavaScript
- Browser speichert die Position in der URL

### Margin-Left auf Body
- Schafft Platz für die Sidebar
- Verhindert, dass Inhalte unter der Sidebar versteckt werden
- Alle Inhalte sind lesbar

## Problem & Lösung

**Problem:** Sidebar verdeckt den Inhalt
**Lösung:** `body { margin-left: 200px; }`
- 200px = 180px Sidebar + 20px Abstand

## Styling Details

```css
.category-button {
    transition: all 0.3s ease;  /* Sanfte Animationen */
    border-left: 3px solid transparent;  /* Unsichtbarer Border */
}

.category-button:hover {
    border-left-color: #7fd3c7;  /* Zeigt grüne Farbe bei Hover */
    transform: translateX(5px);  /* Rückt nach rechts */
}
```

Dies erzeugt einen schönen Hover-Effekt, ohne JavaScript zu brauchen!
